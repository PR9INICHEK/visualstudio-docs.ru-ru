---
title: Развертывание доменного языка с использование MSI и VSIX
ms.date: 11/04/2016
ms.topic: how-to
author: JoshuaPartlow
ms.author: joshuapa
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6d4de8d7560cb43115a30e29516e0e88b4d02d21
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "85542620"
---
# <a name="msi-and-vsix-deployment-of-a-dsl"></a>Развертывание доменного языка с использование MSI и VSIX
Вы можете установить доменный язык на своем компьютере или на других компьютерах. Visual Studio уже должна быть установлена на целевом компьютере.

## <a name="choosing-between-vsix-and-msi-deployment"></a><a name="which"></a>Выбор между развертыванием VSIX и MSI
 Существует два способа развертывания предметно-ориентированного языка:

|Метод|Преимущества|
|-|-|
|VSX (расширение Visual Studio)|Простота развертывания: Скопируйте и выполните **VSIX** файл из проекта DslPackage.<br /><br /> Дополнительные сведения см. [в статье Установка и удаление DSL с помощью VSX](#Installing).|
|MSI (файл установщика)|— Позволяет пользователю открыть Visual Studio, дважды щелкнув файл DSL.<br />— Связывает значок с типом файла DSL на конечном компьютере.<br />— Связывает XSD (схему XML) с типом файла DSL. Это позволяет избежать предупреждений при загрузке файла в Visual Studio.<br /><br /> Чтобы создать MSI-файл, необходимо добавить в решение проект установки.<br /><br /> Дополнительные сведения см. в разделе [Развертывание DSL с помощью MSI-файла](#msi).|

## <a name="install-and-uninstall-a-dsl-by-using-the-vsx"></a><a name="Installing"></a>Установка и удаление DSL с помощью VSX

При установке DSL этим методом пользователь может открыть файл DSL в Visual Studio, но файл нельзя открыть из проводника Windows.

### <a name="to-install-a-dsl-by-using-the-vsx"></a>Установка DSL с помощью VSX

1. Откройте **VSIX** файл, созданный проектом пакета DSL:

   1. В **Обозреватель решений**щелкните правой кнопкой мыши проект **DslPackage** и выберите пункт **Открыть папку в проводнике**.

   2. Откройте файл ** \\ \* \\ bin**_йоурпрожект_**. DslPackage. VSIX**

2. Скопируйте **VSIX** файл на конечный компьютер, на который необходимо установить DSL. Это может быть как ваш собственный компьютер, так и любой другой.

   - На целевом компьютере должен быть установлен один из выпусков [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] , поддерживающий DSL во время выполнения. Дополнительные сведения см. в разделе [Поддерживаемые выпуски Visual Studio для визуализации & моделирования SDK](../modeling/supported-visual-studio-editions-for-visualization-amp-modeling-sdk.md).

   - На целевом компьютере должен быть указан один из выпусков Visual Studio, указанный в **дслпаккаже\саурце.екстенсионс.манифест**.

3. На целевом компьютере дважды щелкните **VSIX** -файл.

    Откроется**установщик расширений Visual Studio** , который устанавливает расширение.

4. Запустите или перезапустите [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].

5. Чтобы протестировать DSL, используйте Visual Studio для создания нового файла с расширением, определенным для вашего DSL.

### <a name="to-uninstall-a-dsl-that-was-installed-by-using-vsx"></a>Удаление DSL, установленного с помощью VSX

1. В меню **Сервис** щелкните **Расширения и обновления**.

2. Разверните узел **Установленные расширения**.

3. Выберите расширение, в котором определен DSL, и нажмите кнопку **Удалить**.

   В редких случаях не удается загрузить неисправное расширение, в результате чего в окне ошибок создается отчет, который не отображается в диспетчере расширений. В этом случае расширение можно удалить, удалив файл из следующей папки:

   *LocalAppData* **\Microsoft\VisualStudio\10.0\Extensions**

## <a name="deploying-a-dsl-in-an-msi"></a><a name="msi"></a>Развертывание DSL в MSI
 Определив файл MSI (установщик Windows) для DSL, можно разрешить пользователям открывать файлы DSL из проводника Windows. Можно также связать значок и краткое описание с расширением имени файла. Кроме того, MSI может установить XSD, который можно использовать для проверки файлов DSL. При необходимости можно добавить в MSI другие компоненты, которые будут установлены одновременно.

 Дополнительные сведения о файлах MSI и других вариантах развертывания см. в разделе [развертывание приложений, служб и компонентов](../deployment/deploying-applications-services-and-components.md).

 Чтобы создать MSI, добавьте в решение Visual Studio проект установки. Самый простой способ создать проект установки — использовать шаблон CreateMsiSetupProject.tt, который можно загрузить с [сайта VMSDK](https://code.msdn.microsoft.com/Visualization-and-Modeling-313535db).

### <a name="to-deploy-a-dsl-in-an-msi"></a>Развертывание DSL в MSI

1. Задайте `InstalledByMsi` в манифесте расширения. Это предотвращает установку и удаление VSX, кроме MSI. Это важно, если в MSI будут включены другие компоненты.

   1. Открыть Дслпаккаже\саурце.екстенсион.ТТ

   2. Вставьте следующую строку перед `<SupportedProducts>` :

       ```xml
       <InstalledByMsi>true</InstalledByMsi>
       ```

2. Создайте или измените значок, который будет представлять ваш DSL в проводнике Windows. Например, Edit **дслпаккаже\ресаурцес\филе.ИКО**

3. Убедитесь в правильности следующих атрибутов DSL:

   - В обозревателе DSL щелкните корневой узел, а затем в окно свойств проверьте следующее:

       - Описание

       - Версия

   - Щелкните узел **редактора** и в окно свойств щелкните **значок**. Задайте значение для ссылки на файл значка в **дслпаккаже\ресаурцес**, например **File. ico.**

   - В меню **Сборка** откройте **Configuration Manager**и выберите конфигурацию, которую требуется собрать, например **выпуск** или **отладку**.

4. Перейдите на [домашнюю страницу SDK визуализации и моделирования](https://code.msdn.microsoft.com/Visualization-and-Modeling-313535db)и на вкладке **Downloads (загрузки** ) Скачайте **CreateMsiSetupProject.TT**.

5. Добавьте **CreateMsiSetupProject.TT** в проект DSL.

    Visual Studio создаст файл с именем **креатемсисетуппрожект. vdproj**.

6. В проводнике Windows скопируйте DSL \\ *. vdproj в новую папку с именем Setup.

    (Если нужно, теперь можно исключить CreateMsiSetupProject.tt из проекта DSL.)

7. В **Обозреватель решений**добавьте **Setup \\ \* . vdproj** в качестве существующего проекта.

8. В меню **проект** выберите пункт **зависимости проекта**.

    В диалоговом окне **зависимости проекта** выберите проект установки.

    Установите флажок рядом с **DslPackage**.

9. Повторно создайте решение.

10. В проводнике Windows выберите в проекте установки созданный MSI файл.

     Скопируйте MSI-файл на компьютер, на котором требуется установить DSL. Дважды щелкните файл MSI. Запуск установщика.

11. На конечном компьютере создайте новый файл с расширением DSL. Проверьте следующее:

    - В представлении списка проводника Windows файл отображается с указанными значком и описанием.

    - Если дважды щелкнуть файл, Visual Studio запустится и откроет файл DSL в редакторе DSL.

    При желании можно создать проект установки вручную, а не использовать текстовый шаблон. Пошаговое руководство, включающее эту процедуру, см. в главе 5 [лаборатории SDK визуализации и моделирования](https://code.msdn.microsoft.com/DSLToolsLab/Release/ProjectReleases.aspx?ReleaseId=4207).

### <a name="to-uninstall-a-dsl-that-was-installed-from-an-msi"></a>Удаление DSL, установленного из MSI

1. В Windows откройте панель управления **программы и компоненты** .

2. Удалите DSL.

3. Перезапустите Visual Studio.
