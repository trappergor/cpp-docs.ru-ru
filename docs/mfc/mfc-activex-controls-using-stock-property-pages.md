---
title: 'Элементы ActiveX в MFC: Использование стандартных страниц свойств | Документация Майкрософт'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: 6fadc159f0924c3714616778cd1fd148b5ff0e84
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423097"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>Элементы управления ActiveX в MFC. Использование стандартных страниц свойств

В этой статье рассматриваются страницы стандартных свойств, доступных для элементов управления ActiveX и их использование.

>[!IMPORTANT]
> ActiveX — это устаревшая технология, которая не следует использовать для разработки новых приложений. Дополнительные сведения о современных технологий, которые следуют за ActiveX, см. в разделе [элементы управления ActiveX](activex-controls.md).

Дополнительные сведения об использовании страницы свойств в элементе управления ActiveX см. в разделе со следующими статьями:

- [Элементы ActiveX в MFC. Страницы свойств](../mfc/mfc-activex-controls-property-pages.md)

- [Элементы ActiveX в MFC. Добавление дополнительной страницы пользовательских свойств](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC предоставляет три стандартных страниц свойств для использования с элементами управления ActiveX: `CLSID_CColorPropPage`, `CLSID_CFontPropPage`, и `CLSID_CPicturePropPage`. Эти страницы пользовательского интерфейса для стандартных цвета, шрифта и свойствах изображения, соответственно.

Чтобы включить эти страницы свойств в элемент управления, добавьте код, который инициализирует элемент управления массив ИД страницы свойств их идентификаторы. В следующем примере, этот код находится в файле реализации элемента управления (. (CPP) инициализирует этот массив должен содержать все три стандартных страниц свойств и страницу свойств по умолчанию (с именем `CMyPropPage` в этом примере):

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

Обратите внимание на то, что число страниц свойств, в begin_proppageids-макрос, — 4. Представляет количество страниц свойств, поддерживаемых элементом управления ActiveX.

После внесения этих изменений, перестройте проект. Элемент управления теперь имеет страницы свойств для шрифта, фотографии и свойства цвета.

> [!NOTE]
>  Если страницы стандартных свойств элемента управления будет недоступна, возможно, так как библиотеки DLL MFC (MFCxx.DLL) не был правильно зарегистрирован с текущей операционной системы. Это обычно происходит из установки Visual C++ в разделе, отличном от того, в настоящее время под управлением операционной системы.

> [!TIP]
>  Если ваши страницы стандартных свойств не отображаются (см. Примечание в предыдущем), регистрации библиотеки DLL, запустив RegSvr32.exe из командной строки с именем полный путь к библиотеке DLL.

## <a name="see-also"></a>См. также

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Добавление стандартных свойств](../mfc/mfc-activex-controls-adding-stock-properties.md)

