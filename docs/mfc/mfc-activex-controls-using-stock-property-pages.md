---
title: Элементы управления ActiveX в MFC. Использование стандартных страниц свойств
ms.date: 09/12/2018
f1_keywords:
- CLSID_CPicturePropPage
- CLSID_CColorPropPage
- CLSID_CFontPropPage
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
ms.openlocfilehash: 13a0edb72657c9ffad00dcb909019bdfe4b87e11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358201"
---
# <a name="mfc-activex-controls-using-stock-property-pages"></a>Элементы управления ActiveX в MFC. Использование стандартных страниц свойств

В этой статье рассматриваются страницы свойств запасов, доступные для элементов управления ActiveX, и способы их использования.

>[!IMPORTANT]
> ActiveX является устаревшей технологией, которая не должна использоваться для новых разработок. Для получения дополнительной информации о современных технологиях, которые заменяли ActiveX, [см.](activex-controls.md)

Для получения дополнительной информации об использовании страниц свойств в элементе управления ActiveX см.

- [Элементы ActiveX в MFC. Страницы свойств](../mfc/mfc-activex-controls-property-pages.md)

- [Элементы управления ActiveX в MFC. Добавление дополнительной страницы пользовательских свойств](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

MFC предоставляет три страницы фондового свойства `CLSID_CColorPropPage` `CLSID_CFontPropPage`для `CLSID_CPicturePropPage`использования с ActiveX управления: , и . На этих страницах отображается пользовательский интерфейс для свойств стокового цвета, шрифта и изображения соответственно.

Чтобы включить эти страницы свойств в элемент управления, добавьте их идонов в код, который инициализирует массив идотов страницы свойств. В следующем примере этот код, расположенный в файле реализации элемента управления (. CPP), инициализирует массив, чтобы содержать все три страницы фондового свойства и страницу свойств по умолчанию (названо `CMyPropPage` в этом примере):

[!code-cpp[NVC_MFC_AxOpt#21](../mfc/codesnippet/cpp/mfc-activex-controls-using-stock-property-pages_1.cpp)]

Обратите внимание, что количество страниц свойств, в BEGIN_PROPPAGEIDS макрос, составляет 4. Это представляет собой количество страниц свойств, поддерживаемых управлением ActiveX.

После внесения этих изменений восстановите свой проект. Теперь элемент управления имеет страницы свойств для шрифта, изображения и цветовых свойств.

> [!NOTE]
> Если страницы контрольного акционерного фонда не доступны, это может быть связано с тем, что MFC DLL (MFCxx.DLL) не была должным образом зарегистрирована в текущей операционной системе. Это обычно приводит к установке Visual C е под операционную систему, отличающуюся от той, которая в настоящее время работает.

> [!TIP]
> Если страницы свойств акций не видны (см. предыдущее Примечание), зарегистрируйте DLL, запустив RegSvr32.exe от командной строки с полным названием пути к DLL.

## <a name="see-also"></a>См. также раздел

[Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)<br/>
[Элементы ActiveX в MFC. Добавление стандартных свойств](../mfc/mfc-activex-controls-adding-stock-properties.md)
