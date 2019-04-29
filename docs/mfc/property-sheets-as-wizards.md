---
title: Вкладки свойств как мастера
ms.date: 11/04/2016
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
ms.openlocfilehash: c60148c099b34993bef0c9808e6561e37c26cc7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391365"
---
# <a name="property-sheets-as-wizards"></a>Вкладки свойств как мастера

Основной характеристикой листа свойств мастера является то, что навигации предоставляется с помощью кнопки "Далее" или "Готово", "," и "Отмена" вместо вкладок. Необходимо вызвать [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) перед вызовом [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) на объект страницы свойств, чтобы воспользоваться преимуществами этой функции.

Пользователь получает же [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) и [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) уведомления при перемещении с одной страницы на другую страницу. Далее и кнопки Готово являются взаимно исключают друг друга элементов управления; то есть только один из них будет отображаться одновременно. На первой странице должен быть включен "Далее". Если пользователь находится на последней странице, должен быть включен "Готово". Это не выполняется автоматически платформой. Должен быть вызван [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) на последней странице, чтобы добиться этого.

Чтобы отобразить все кнопки по умолчанию, необходимо показать кнопку "Готово" и переместите кнопку Далее. Переместите кнопку "Назад", чтобы его относительное положение кнопок сохраняется.

## <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>См. также

[Страницы свойств](../mfc/property-sheets-mfc.md)
