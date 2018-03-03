---
title: "Вкладки свойств как мастера | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- property sheets, as wizards
ms.assetid: 1ea66ecb-23b0-484a-838d-58671a2999b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65aedc5dbeb8a740d5713983f66eefe693864937
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="property-sheets-as-wizards"></a>Вкладки свойств как мастера
Основной характеристикой таблицы свойств мастера является предоставление навигации с кнопками Далее или Готово и Отмена вместо символов табуляции. Необходимо вызвать [CPropertySheet::SetWizardMode](../mfc/reference/cpropertysheet-class.md#setwizardmode) перед вызовом [CPropertySheet::DoModal](../mfc/reference/cpropertysheet-class.md#domodal) на объект вкладки свойств, чтобы воспользоваться преимуществами этой функции.  
  
 Пользователь получает же [CPropertyPage::OnSetActive](../mfc/reference/cpropertypage-class.md#onsetactive) и [CPropertyPage::OnKillActive](../mfc/reference/cpropertypage-class.md#onkillactive) уведомления при перемещении с одной страницы на другую страницу. Далее и Готово кнопок являются взаимоисключающими элементов управления; то есть только один из них будет отображаться одновременно. На первой странице должен быть включен "Далее". Если пользователь находится на последней странице, должен быть включен "Готово". Это не выполняется автоматически платформой. Необходимо вызвать [CPropertySheet::SetWizardButton](../mfc/reference/cpropertysheet-class.md#setwizardbuttons) на последней странице, чтобы добиться этого.  
  
 Чтобы отобразить все кнопки по умолчанию, необходимо отображать кнопку "Готово" и перемещение кнопки «Далее». Для обеспечения его относительного расположения кнопок переместите кнопку "Назад".  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#5](../mfc/codesnippet/cpp/property-sheets-as-wizards_1.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../mfc/property-sheets-mfc.md)

