---
title: Часто переопределяемые функции-члены | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aabc88db4fcb2a484ca44feea8fcdf7727e23a16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431415"
---
# <a name="commonly-overridden-member-functions"></a>Часто переопределяемые функции-члены

В следующей таблице перечислены наиболее вероятной функции-члены для переопределения в вашей `CDialog`-производного класса.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Часто переопределяемые функции-члены класса CDialog

|Функция-член|Она отвечает на сообщение|Цель переопределения|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|Инициализация элементов управления диалогового окна.|
|`OnOK`|**BN_CLICKED** для кнопки **IDOK**|Ответить, когда пользователь нажимает кнопку "ОК".|
|`OnCancel`|**BN_CLICKED** для кнопки **IDCANCEL**|Ответить, когда пользователь нажимает кнопку "Отмена".|

`OnInitDialog`, `OnOK`, и `OnCancel` — это виртуальные функции. Чтобы переопределить их, переопределяющую функцию объявить в классе производном диалоговое окно с помощью [окно "Свойства"](/visualstudio/ide/reference/properties-window).

`OnInitDialog` вызывается непосредственно перед отображением диалоговое окно. Необходимо вызвать метод по умолчанию `OnInitDialog` обработчик из переопределение — обычно это первое действие в обработчике. По умолчанию `OnInitDialog` возвращает **TRUE** для указания, что фокус должен быть задан для первого элемента управления в диалоговом окне.

`OnOK` обычно переопределяется для немодального, но не модальные диалоговые окна. Если вы Переопределите этот обработчик для модального диалогового окна, вызовите версии базового класса из переопределение, чтобы убедиться, что `EndDialog` вызывается — или вызвать `EndDialog` самостоятельно.

`OnCancel` обычно переопределяется для немодальных диалоговых окон.

См. Дополнительные сведения об этих функций-членов класса [CDialog](../mfc/reference/cdialog-class.md) в *Справочник по библиотеке MFC* и обсуждение [жизненного цикла в диалоговом окне](../mfc/life-cycle-of-a-dialog-box.md).

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Часто добавляемые функции-члены](../mfc/commonly-added-member-functions.md)
