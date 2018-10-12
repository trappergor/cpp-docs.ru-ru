---
title: Добавление метода (Visual C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- methods [C++], adding
ms.assetid: 4ba4e45f-fa38-4d5e-af44-cbec0a7ab558
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1b0082ef7df5ddcc698741ebd4f3fb5455b6614d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390712"
---
# <a name="adding-a-method--visual-c"></a>Добавление метода (Visual C++)

Вы можете использовать [мастер добавления метода](../ide/add-method-wizard.md) для добавления метода в интерфейс в проекте. Если проект содержит класс, сопоставленный с интерфейсом, мастер изменяет и этот класс.

### <a name="to-add-a-method-to-your-object"></a>Добавление метода в объект

1. В представлении классов разверните узел проекта, чтобы отобразить интерфейс, в который нужно добавить метод.

   > [!NOTE]
   > Вы также можете добавлять методы в disp-интерфейсы, которые, если только проект не имеет атрибуты, находятся в узле библиотеки.

1. Щелкните имя интерфейса правой кнопкой мыши.

1. В контекстном меню выберите команду **Добавить**, а затем — **Добавить метод**.

1. В мастере добавления метода укажите сведения для создания метода.

1. Задайте параметры IDL для этого метода на странице [Атрибуты IDL](../ide/idl-attributes-add-method-wizard.md) мастера.

1. Нажмите кнопку **Готово**, чтобы добавить метод.

## <a name="see-also"></a>См. также

[Создание интерфейса COM](../ide/creating-a-com-interface-visual-cpp.md)<br>
[Редактирование интерфейса COM](../ide/editing-a-com-interface.md)