---
title: Работа с Subversion
description: Использование Subversion в Visual Studio для Mac.
author: heiligerdankgesang
ms.author: dominicn
ms.date: 05/06/2018
ms.assetid: 2400ED9C-6236-4C0A-A3AB-9D7CBE1F0CF4
ms.openlocfilehash: e5a9dd8120dd312bfc3e1c8905a725a58cca0e92
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2020
ms.locfileid: "74983519"
---
# <a name="working-with-subversion"></a>Работа с Subversion

Subversion — это централизованная система управления версиями, позволяющая получать для изменения мастер-копию централизованных данных. В отличие от Git при получении репозитория Subversion не клонирует его целиком, а лишь создает моментальный снимок на данный момент времени.

Subversion использует модель "копирование-изменение-слияние", чтобы пользователи могли одновременно работать с одним репозиторием. Это означает, что каждый пользователь создает локальную (рабочую) копию централизованных данных, которую можно использовать независимо. Изменения в рабочих копиях пользователей объединяются в хронологическом порядке.

Например, предположим, что пользователи А и Б получают для изменения копию из удаленного репозитория, а затем изменяют эти файлы. Пользователь А завершает изменения и фиксирует их удаленно. Прежде чем пользователь Б сможет зафиксировать свою работу, ему потребуется обновить свою рабочую копию изменениями из удаленного расположения, то есть выполнить слияние с изменениями пользователя А.

В следующих разделах рассматривается использование Subversion для управления версиями в Visual Studio для Mac.

На следующем рисунке показаны параметры, предоставляемые в Visual Studio для Mac с помощью пункта меню "Управление версиями":

![Пункты меню "Управление версиями"](media/version-control-svnVersionControlMenu.png)

## <a name="checkout"></a>Извлечение...

Прежде чем приступать к работе с удаленным репозиторием Subversion, извлеките его для создания рабочей копии этого каталога на локальном компьютере.

Чтобы узнать об использовании функции **извлечения** в Visual Studio для Mac, выполните действия, описанные в разделе [Настройка репозитория Subversion](set-up-subversion-repository.md).

## <a name="update-solution"></a>Обновление решения

При использовании удаленного репозитория важно помнить, что другие пользователи могут изменять файлы, делая вашу рабочую копию устаревшей. Во избежание таких конфликтов перед началом работы и фиксацией рекомендуется всегда вытягивать все изменения из репозитория в ваше решение. Для этого выберите **Управление версиями > Обновить решение**.

## <a name="review-solution-and-commit"></a>Проверка решения и фиксация

Чтобы проверить изменения в файлах, используйте вкладки "Изменения", "Обвинение", "Журнал" и "Слияние" для каждого документа, как показано на следующем рисунке:

![Вкладки управления версиями](media/version-control-vcTabs.png)

Для проверки всех изменений в проекте выберите пункт меню **Управление версиями > Review Solution and Commit** (Проверить решение и фиксировать):

![Проверка решения](media/version-control-vcStatus.png)

Это позволяет просмотреть все изменения в каждом файле проекта с возможностью отменить изменения, создать исправление или фиксировать.

Чтобы зафиксировать файл в удаленном репозитории, нажмите кнопку "Фиксировать...", введите сообщение фиксации и подтвердите нажатием кнопки фиксации:

![Фиксация файла](media/version-control-svnCommit.png)

Это позволяет отправить изменения в репозиторий, где они создают новую редакцию всех изменений.

## <a name="see-also"></a>См. также раздел

- [Настройка репозитория Subversion](set-up-subversion-repository.md)
