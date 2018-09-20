---
title: Вставка формы в проект | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 83606041250dafed0ef57eb4eea18d7314e0bbef
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429270"
---
# <a name="inserting-a-form-into-a-project"></a>Вставка формы в проект

Forms предоставляют удобный контейнер для элементов управления. Можно легко вставить форму на базе MFC в приложении до тех пор, пока приложение поддерживает библиотеки MFC.

### <a name="to-insert-a-form-into-your-project"></a>Вставка формы в проект

1. Из представления классов выберите проект, к которому вы хотите добавить форму и щелкните правой кнопкой мыши.

1. В контекстном меню, щелкните **добавить** и нажмите кнопку **Добавление класса**.

     Если **новую форму** команда недоступна, проект может быть основана на Active Template Library (ATL). Чтобы добавить форму в проект ATL, необходимо выполнить [настроить определенные параметры](../atl/reference/application-settings-atl-project-wizard.md) при первоначальном создании проекта.

1. Из **MFC** папку, нажмите кнопку **класс MFC**.

1. С помощью мастера классов MFC, заставить новый класс являются производными от [CFormView](../mfc/reference/cformview-class.md).

Visual C++ добавляет формы на приложение, открыв его в редакторе диалоговых окон, таким образом, можно начать добавление элементов управления и работает над ее общей структуры.

Вы можете выполнить следующие дополнительные действия (не применимо для приложений на основе диалоговых окон):

1. Переопределить `OnUpdate` функция-член.

1. Реализуйте функцию-член для перемещения данных из представления в документ.

1. Создание `OnPrint` функция-член.

## <a name="see-also"></a>См. также

[Представления форм](../mfc/form-views-mfc.md)

