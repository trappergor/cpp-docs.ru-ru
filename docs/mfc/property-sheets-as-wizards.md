---
title: Вкладки свойств как мастера | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73b6b0462012fc54b3bd6f2cb22422f5b1431288
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46374214"
---
# <a name="property-sheets-as-wizards"></a>Вкладки свойств как мастера

Основной характеристикой листа свойств мастера является то, что навигации предоставляется с помощью кнопки "Далее" или "Готово", "," и "Отмена" вместо вкладок. Необходимо вызвать [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) перед вызовом [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) на объект страницы свойств, чтобы воспользоваться преимуществами этой функции.

Пользователь получает же [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) и [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) уведомления при перемещении с одной страницы на другую страницу. Далее и кнопки Готово являются взаимно исключают друг друга элементов управления; то есть только один из них будет отображаться одновременно. На первой странице должен быть включен "Далее". Если пользователь находится на последней странице, должен быть включен "Готово". Это не выполняется автоматически платформой. Должен быть вызван [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) на последней странице, чтобы добиться этого.

Чтобы отобразить все кнопки по умолчанию, необходимо показать кнопку "Готово" и переместите кнопку Далее. Переместите кнопку "Назад", чтобы его относительное положение кнопок сохраняется.

## <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]

## <a name="see-also"></a>См. также

[Страницы свойств](../mfc/property-sheets-mfc.md)

