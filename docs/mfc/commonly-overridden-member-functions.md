---
title: Часто переопределяемые функции-члены
ms.date: 09/06/2019
helpviewer_keywords:
- CDialog class [MFC], members
- OnInitDialog function
- dialog classes [MFC], commonly overridden member functions
- OnCancel function
- overriding, dialog class members
- OnOK function
- MFC dialog boxes [MFC], overriding member functions
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
ms.openlocfilehash: f63dd6079b96181305f3207d4a1ef823df8d8ba4
ms.sourcegitcommit: 3caf5261b3ea80d9cf14038c116ba981d655cd13
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/11/2019
ms.locfileid: "70907693"
---
# <a name="commonly-overridden-member-functions"></a>Часто переопределяемые функции-члены

В следующей таблице перечислены наиболее вероятные функции-члены для переопределения в `CDialog`классе, производном от.

### <a name="commonly-overridden-member-functions-of-class-cdialog"></a>Часто переопределенные функции элементов класса CDialog

|Функция Member|Сообщение, на которое он отвечает|Назначение переопределения|
|---------------------|----------------------------|-----------------------------|
|`OnInitDialog`|**WM_INITDIALOG**|Инициализируйте элементы управления диалогового окна.|
|`OnOK`|**BN_CLICKED** для кнопки **идок**|Ответ, когда пользователь нажимает кнопку ОК.|
|`OnCancel`|**BN_CLICKED** для кнопки **идканцел**|Реагирует, когда пользователь нажимает кнопку "Отмена".|

`OnInitDialog`, `OnOK` и`OnCancel` являются виртуальными функциями. Чтобы переопределить их, объявите переопределяющую функцию в производном классе диалогового окна с помощью [мастера классов MFC](reference/mfc-class-wizard.md).

`OnInitDialog`вызывается непосредственно перед отображением диалогового окна. Необходимо вызвать обработчик по умолчанию `OnInitDialog` из переопределения, обычно как первое действие в обработчике. По умолчанию `OnInitDialog` возвращает **значение true** , указывающее, что фокус должен быть установлен на первый элемент управления в диалоговом окне.

`OnOK`обычно переопределяется для немодальных, но не модальных диалоговых окон. При переопределении этого обработчика для модального диалогового окна вызывайте версию базового класса из переопределения, чтобы убедиться, `EndDialog` что вызывается, или `EndDialog` вызовите себя самостоятельно.

`OnCancel`обычно переопределяется для немодальных диалоговых окон.

Дополнительные сведения об этих функциях-членах см. в разделе класс [CDialog](../mfc/reference/cdialog-class.md) в *справочнике по MFC* и обсуждении [жизненного цикла диалогового окна](../mfc/life-cycle-of-a-dialog-box.md).

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Часто добавляемые функции-члены](../mfc/commonly-added-member-functions.md)
