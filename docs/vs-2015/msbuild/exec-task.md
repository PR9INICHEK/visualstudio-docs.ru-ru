---
title: Задача Exec | Документация Майкрософт
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#Exec
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- Exec task [MSBuild]
- MSBuild, Exec task
ms.assetid: c9b7525a-b1c9-40fc-8bce-77a5b8f960d8
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd84ea51e4d7cf699ee4fd78b9349985e95d5669
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "47573468"
---
# <a name="exec-task"></a>Задача Exec
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Последнюю версию этого раздела можно найти в [задача Exec](https://docs.microsoft.com/visualstudio/msbuild/exec-task).  
  
  
Запускает заданную программу или команду с использованием заданных аргументов.  
  
## <a name="parameters"></a>Параметры  
 В следующей таблице приводятся параметры для задачи `Exec`.  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`Command`|Обязательный параметр `String` .<br /><br /> Выполняемые команды. Это могут быть системные команды (например, attrib) или исполняемые файлы (например, program.exe, runprogram.bat или setup.msi).<br /><br /> Этот параметр может содержать несколько строк с командами. Кроме того, можно поместить несколько команд в пакетный файл и запустить его с помощью этого параметра.|  
|`CustomErrorRegularExpression`|Необязательный параметр `String` .<br /><br /> Указывает регулярное выражение, которое используется для выявления ошибочных строк в выходных данных средства. Это полезно при работе со средствами, которые создают нестандартно отформатированные выходные данные.|  
|`CustomWarningRegularExpression`|Необязательный параметр `String` .<br /><br /> Указывает регулярное выражение, которое используется для выявления строк с предупреждениями в выходных данных средства. Это полезно при работе со средствами, которые создают нестандартно отформатированные выходные данные.|  
|`ExitCode`|Необязательный выходной параметр `Int32`, доступный только для чтения.<br /><br /> Задает код выхода, предоставляемый выполняемой командой.|  
|`IgnoreExitCode`|Необязательный параметр `Boolean` .<br /><br /> Если он имеет значение `true`, то задача игнорирует код выхода, передаваемый выполняемой командой. В противном случае задача возвращает `false`, если выполняемая команда возвращает отличный от нуля код выхода.|  
|`IgnoreStandardErrorWarningFormat`|Необязательный параметр `Boolean` .<br /><br /> Если он имеет значение `false`, из выходных данных отбираются строки, соответствующие стандартному формату ошибок и (или) предупреждений. Эти строки заносятся в журнал как ошибки или предупреждения соответственно. Значение `true` отключает это поведение.|  
|`Outputs`|Необязательный выходной параметр <xref:Microsoft.Build.Framework.ITaskItem>`[]` .<br /><br /> Содержит выходные элементы задачи. Задача `Exec` не устанавливает их самостоятельно. Вместо этого вы можете предоставить значения, которые будут переданы как выходные данные, чтобы использовать их в последующих элементах проекта.|  
|`StdErrEncoding`|Необязательный выходной параметр `String`.<br /><br /> Указывает кодировку перехватываемого стандартного потока ошибки для задачи. По умолчанию используется текущая кодировка выходной консоли.|  
|`StdOutEncoding`|Необязательный выходной параметр `String`.<br /><br /> Указывает кодировку перехватываемого стандартного потока вывода для задачи. По умолчанию используется текущая кодировка выходной консоли.|  
|`WorkingDirectory`|Необязательный параметр `String` .<br /><br /> Указывает каталог, в котором будет выполняться команда.|  
  
## <a name="remarks"></a>Примечания  
 Эта задача полезна, если отсутствует специальная задача [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] для задания, которое вы хотите выполнить. Учтите, что задача `Exec`, в отличие от более специализированных задач, не может получать выходные данные из средства или команды, для которой она выполняется.  
  
 Задача `Exec` вызывает cmd.exe, а не запускает процесс напрямую.  
  
 Помимо перечисленных выше параметров, эта задача наследует параметры от класса <xref:Microsoft.Build.Tasks.ToolTaskExtension>, который, в свою очередь, наследует от класса <xref:Microsoft.Build.Utilities.ToolTask>. Список этих дополнительных параметров и их описания см. в статье [Базовый класс ToolTaskExtension](../msbuild/tooltaskextension-base-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере задача `Exec` выполняет команду.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    <ItemGroup>  
        <Binaries Include="*.dll;*.exe"/>  
    </ItemGroup>  
  
    <Target Name="SetACL">  
        <!-- set security on binaries-->  
        <Exec Command="echo y| cacls %(Binaries.Identity) /G everyone:R"/>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>См. также  
 [Задачи](../msbuild/msbuild-tasks.md)   
 [Справочные сведения о задачах](../msbuild/msbuild-task-reference.md)


