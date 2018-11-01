---
title: Использование элемента управления RichEdit 1.0 с MFC
ms.date: 11/04/2016
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls [C++], RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
ms.openlocfilehash: 080ad995b9c7a041337d9b296d6ef8906e7f20ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468319"
---
# <a name="using-the-richedit-10-control-with-mfc"></a>Использование элемента управления RichEdit 1.0 с MFC

Чтобы использовать элемент управления RichEdit, необходимо сначала вызвать [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) загрузить элемент управления RichEdit 2.0 (библиотеки RICHED20. Библиотека DLL), или вызвать [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) для загрузки более старых элемента управления RichEdit 1.0 (RICHED32. БИБЛИОТЕКА DLL).

Вы можете использовать текущий [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) класса с помощью более старых элемента управления RichEdit 1.0, но `CRichEditCtrl` предназначена только для поддержки управления RichEdit 2.0. Поскольку RichEdit 1.0 и RichEdit 2.0 очень похожи, будет работать большинство методов; Тем не менее Обратите внимание, что существуют некоторые различия между 1.0 и 2.0 элементы управления, поэтому некоторые методы могут работать неправильно или вообще не работать.

## <a name="requirements"></a>Требования

MFC

## <a name="see-also"></a>См. также

[Устранение неполадок редактора диалоговых окон](../windows/troubleshooting-the-dialog-editor.md)<br/>
[Редактор диалоговых окон](../windows/dialog-editor.md)