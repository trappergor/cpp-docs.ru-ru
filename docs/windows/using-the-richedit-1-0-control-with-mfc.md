---
title: Использование элемента управления RichEdit 1.0 с MFC | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RichEdit 1.0 control
- rich edit controls, RichEdit 1.0
ms.assetid: 5a9060dd-44d8-4ef3-956e-16152f7e23d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d2d45de1c6bd986c2bf509ce601f80fcd3721599
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="using-the-richedit-10-control-with-mfc"></a>Использование элемента управления RichEdit 1.0 с MFC
С помощью элемента управления RichEdit, необходимо сначала вызвать [AfxInitRichEdit2](../mfc/reference/application-information-and-management.md#afxinitrichedit2) для загрузки элемента управления RichEdit 2.0 (библиотеки RICHED20. (DLL) или вызвать [AfxInitRichEdit](../mfc/reference/application-information-and-management.md#afxinitrichedit) для загрузки более старых элемента управления RichEdit 1.0 (RICHED32. БИБЛИОТЕКА DLL).  
  
 Может использовать текущий [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) класса с помощью старых элемента управления RichEdit 1.0, но **CRichEditCtrl** предназначен только для поддержки управления RichEdit 2.0. Большинство методов будет работать, потому что RichEdit 1.0 и RichEdit 2.0 очень похожи, Однако обратите внимание, что существуют некоторые различия между 1.0 и 2.0 элементами управления, поэтому некоторые методы могут работать неправильно или вообще не работает.  
  
## <a name="requirements"></a>Требования  
 MFC  
  
## <a name="see-also"></a>См. также  
 [Устранение неполадок редактора диалоговых окон](../windows/troubleshooting-the-dialog-editor.md)   
 [Редактор диалоговых окон](../windows/dialog-editor.md)

