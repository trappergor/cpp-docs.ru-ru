---
title: 'Элементы управления ActiveX MFC: Использование стандартных страниц свойств | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
dev_langs:
- C++
helpviewer_keywords:
- picture stock property pages [MFC]
- CLSID_CFontPropPage [MFC]
- color stock property pages [MFC]
- CLSID_CColorPropPage [MFC]
- fonts [MFC], ActiveX controls
- stock properties [MFC], stock property pages
- CLSID_CPicturePropPage [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 22638d86-ff3e-4124-933e-54b7c2a25968
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e8d54f87e4e018a004bbab503664fa1788f36c2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>Элементы управления ActiveX в MFC. Использование стандартных страниц свойств
Страницы стандартных свойств, доступных для элементов управления ActiveX и их использование описаны в этой статье.  
  
 Дополнительные сведения об использовании страницы свойств в элементе управления ActiveX см. в следующих статьях:  
  
-   [Элементы ActiveX в MFC. Страницы свойств](../mfc/mfc-activex-controls-property-pages.md)  
  
-   [Элементы ActiveX в MFC. Добавление дополнительной страницы пользовательских свойств](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
 MFC предоставляет три стандартных страниц свойств для использования с элементами управления ActiveX: **CLSID_CColorPropPage**, **CLSID_CFontPropPage**, и **CLSID_CPicturePropPage**. Эти страницы пользовательского интерфейса для стандартных цвета, шрифта и свойства изображения соответственно.  
  
 Чтобы включить эти страницы свойств в элемент управления, добавьте их идентификаторы коду, который инициализирует элемент управления массив кодов страницы свойств. В следующем примере этот код находится в файле реализации элемента управления (. CPP) инициализирует массив содержит все три стандартных страниц свойств и страницы свойств по умолчанию (с именем `CMyPropPage` в этом примере):  
  
 [!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]  
  
 Обратите внимание, что число свойств страниц в `BEGIN_PROPPAGEIDS` макрос, равно 4. Представляет количество страниц свойств, поддерживаемых элементом управления ActiveX.  
  
 После внесения этих изменений, перестройте проект. Теперь элемент управления имеет страницы свойств шрифта, изображения и цвет свойства.  
  
> [!NOTE]
>  Если недоступны страницы стандартных свойств элемента управления, возможно, так как библиотеки DLL MFC (MFCxx.DLL) не зарегистрирован должным образом с использованием текущей операционной системы. Это обычно происходит из установки Visual C++ в операционной системе, отличный от того, в настоящее время запущен.  
  
> [!TIP]
>  Если не отображаются страницы стандартных свойств (см. Примечание в предыдущем) зарегистрировать библиотеку DLL, запустив RegSvr32.exe из командной строки с именем полный путь к библиотеке DLL.  
  
## <a name="see-also"></a>См. также  
 [Элементы управления ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Элементы ActiveX в MFC. Добавление стандартных свойств](../mfc/mfc-activex-controls-adding-stock-properties.md)

