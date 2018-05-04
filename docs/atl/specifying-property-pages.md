---
title: Указание страницы свойств (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- ISpecifyPropertyPages
dev_langs:
- C++
helpviewer_keywords:
- ISpecifyPropertyPages method
- property pages, specifying
ms.assetid: ee8678cf-c708-49ab-b0ad-fc2db31f1ac3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8d4cbeaa8ea9a57f9287f2d2fe78c61884ba4a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="specifying-property-pages"></a>Указание страницы свойств
При создании элемента управления ActiveX, часто нужно связать его с помощью страниц свойств, которые могут использоваться для задания свойств элемента управления. Управляет использованием контейнеры **ISpecifyPropertyPages** интерфейс, чтобы узнать, какие страницы свойств можно использовать для задания свойств элемента управления. Необходимо реализовать этот интерфейс на элементе управления.  
  
 Для реализации **ISpecifyPropertyPages** с использованием ATL, выполните следующие действия:  
  
1.  Создайте производный класс от [ISpecifyPropertyPagesImpl](../atl/reference/ispecifypropertypagesimpl-class.md).  
  
2.  Добавьте запись для **ISpecifyPropertyPages** к сопоставлению COM ваш класс.  
  
3.  Добавить [PROP_PAGE](reference/property-map-macros.md#prop_page) входа для сопоставления свойств для каждой страницы, связанный с элементом управления.  
  
> [!NOTE]
>  При создании стандартного элемента управления с помощью [мастер элементов управления ATL](../atl/reference/atl-control-wizard.md), будет достаточно для добавления `PROP_PAGE` записей в схеме сопоставления свойств. Мастер создает необходимый код для других шагов.  
  
 Правильно настроенные контейнеров будет отображать страницы указанное свойство в том же порядке, что `PROP_PAGE` записи в схеме сопоставления свойств. Как правило следует помещать записи страницы стандартных свойств после операции для пользовательских страниц в сопоставлении свойств, чтобы пользователи видели страницы, определенные в элемент управления, сначала.  
  
## <a name="example"></a>Пример  
 Следующий класс календаря управления использует **ISpecifyPropertyPages** интерфейс сообщить контейнеров, которые его свойства могут быть заданы с помощью стандартных цветов и настраиваемые дата страницы.  
  
 [!code-cpp[NVC_ATL_Windowing#72](../atl/codesnippet/cpp/specifying-property-pages_1.h)]  
  
## <a name="see-also"></a>См. также  
 [Страницы свойств](../atl/atl-com-property-pages.md)   
 [Пример ATLPages](../visual-cpp-samples.md)

