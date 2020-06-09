---
title: Добавление элементов управления на вкладку свойств
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], adding to property sheets
- property sheets, adding controls
ms.assetid: 24ad4c0b-c1db-4850-b9f0-34aae8d74571
ms.openlocfilehash: 527c0a5ef6e9dc4fcc9d7668c12e15ec956b0e70
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616063"
---
# <a name="adding-controls-to-a-property-sheet"></a>Добавление элементов управления на вкладку свойств

По умолчанию лист свойств выделяет область окна для страниц свойств, индекс табуляции, а также кнопки ОК, отмена и применить. (Немодальная страница свойств не содержит кнопки ОК, отмена и применить.) На страницу свойств можно добавить другие элементы управления. Например, можно добавить окно предварительного просмотра справа от области страницы свойств, чтобы отобразить сведения о том, как будут выглядеть текущие параметры при применении к внешнему объекту.

Элементы управления можно добавить в диалоговое окно страницы свойств в `OnCreate` обработчике. При размещении дополнительных элементов управления обычно требуется увеличение размера диалогового окна страницы свойств. После вызова базового класса **CPropertySheet:: OnCreate**вызовите [жетвиндоврект](reference/cwnd-class.md#getwindowrect) , чтобы получить ширину и высоту выделенного в настоящий момент окна страницы свойств, разверните размеры прямоугольника и вызовите [мовевиндов](reference/cwnd-class.md#movewindow) , чтобы изменить размер окна страницы свойств.

## <a name="see-also"></a>См. также раздел

[Вкладки свойств](property-sheets-mfc.md)<br/>
[Класс CPropertyPage](reference/cpropertypage-class.md)<br/>
[Класс CPropertySheet](reference/cpropertysheet-class.md)
