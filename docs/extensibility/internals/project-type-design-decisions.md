---
title: Проект Тип Проект Решения (ru) Документы Майкрософт
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project types, project file persistence
- project types, commitment mechanics
- project types, items
- project types, design decisions
ms.assetid: f68671fe-fd7a-4e56-a0b5-330b0f1fedb1
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5e33ac1c4168593b881f799dfdfb94005fb55fc1
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2020
ms.locfileid: "80706363"
---
# <a name="project-type-design-decisions"></a>Проектные решения для типа проекта
Прежде чем создать новый тип проекта, необходимо принять несколько проектных решений относительно типа проекта. Вы должны решить, какие типы элементов будут содержаться в ваших проектах, как будут сохраняться файлы проекта и какую модель обязательств вы будете использовать.

## <a name="project-items"></a>Элементы проекта
 Будет ли ваш проект использовать файлы или абстрактные объекты? Если вы используете файлы, будут ли они базироваться на справочных или каталоговых файлах? Файлы или абстрактные объекты будут локальными или удаленными?

 Элементы в проекте могут быть файлами, или они могут быть более абстрактными объектами, такими как объекты в репозитории базы данных или соединения данных в Интернете. Если элементы являются файлами, проект может быть либо эталонным, либо проектом на основе каталогов.

 В референтных проектах элементы могут отображаться в нескольких проектах. Однако фактический файл, представляющий элемент, находится только в одном каталоге. В проектах, основанных на каталогах, все элементы проекта существуют в структуре каталога.

 Локальные элементы хранятся на том же компьютере, где установлено приложение. Удаленные элементы могут храниться на отдельном сервере в локальной сети или в другом месте в Интернете.

## <a name="project-file-persistence"></a>Настойчивость файлов проекта
 Будут ли данные храниться в обычных плоских файловых системах или в структурированном хранилище? Будут ли открыты файлы с помощью стандартного редактора или конкретного редактора проекта?

 Чтобы сохранить свои данные, большинство приложений сохраняют свои данные в файле, а затем считывают их обратно, когда пользователь должен просмотреть или изменить информацию.

 Структурированное хранилище, также называемое составными файлами, обычно используется, когда нескольким объектам компонентной модели объектов (COM) необходимо хранить свои сохраняющиеся данные в одном файле. При структурированном хранилище несколько различных компонентов программного обеспечения могут совместно хранить один диск.

 У вас есть несколько вариантов, которые следует рассмотреть в отношении настойчивости элементов в проекте. Вы можете выполнить любой из следующих вариантов:

- Сохранить каждый файл индивидуально, когда он был изменен.

- Захват многих транзакций в одной операции **Save.**

- Сохранить файлы локально, а затем опубликовать на сервере или использовать другой подход к сохранению элементов проекта, когда элемент представляет подключение данных к удаленному объекту.

  Для получения дополнительной информации о настойчивости [см.](../../extensibility/internals/project-persistence.md) [Opening and Saving Project Items](../../extensibility/internals/opening-and-saving-project-items.md)

## <a name="project-commitment-model"></a>Модель обязательств по проектам
 Будут ли сохраняющиеся объекты данных открываться в прямом или режиме передачи данных?

 При открытии объектов данных в прямом режиме изменения, внесенные в данные, немедленно включаются или когда пользователь вручную сохраняет файл.

 При открытии объектов данных с помощью режима сданной карты изменения сохраняются во временном местоположении в памяти и не завершаются до тех пор, пока пользователь вручную не решит сохранить файл. В это время все изменения должны происходить вместе или никаких изменений не будет сделано.

## <a name="see-also"></a>См. также
- [Контрольный список. Создание типов проектов](../../extensibility/internals/checklist-creating-new-project-types.md)
- [Открытие и сохранение элементов проекта](../../extensibility/internals/opening-and-saving-project-items.md)
- [Сохранение проекта](../../extensibility/internals/project-persistence.md)
- [Элементы модели проекта](../../extensibility/internals/elements-of-a-project-model.md)
- [Основные компоненты модели проекта](../../extensibility/internals/project-model-core-components.md)
- [Создание типов проектов](../../extensibility/internals/creating-project-types.md)
