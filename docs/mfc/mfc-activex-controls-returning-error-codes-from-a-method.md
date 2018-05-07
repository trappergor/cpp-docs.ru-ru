---
title: 'Элементы управления ActiveX MFC: Возврат кодов ошибок из метода | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- SetNotSupported method, using
- errors [MFC], ActiveX control error codes
- GetNotSupported method [MFC]
- FireError method [MFC]
- SCODE, MFC ActiveX controls
- ThrowError method [MFC]
ms.assetid: 771fb9c9-2413-4dcc-b386-7bc4c4adeafd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 43bf6730cf1b914405f99af6572a0a53cd942ac6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-activex-controls-returning-error-codes-from-a-method"></a>Элементы управления ActiveX в MFC. Возврат кодов ошибок из метода
В этой статье описывается ошибка коды возврата из метода, элемент управления ActiveX.  
  
 Чтобы указать, что произошла ошибка в методе, следует использовать [COleControl::ThrowError](../mfc/reference/colecontrol-class.md#throwerror) функция-член, который принимает `SCODE` (код состояния) как параметр. Можно использовать предварительно определенную `SCODE` или определить один из собственных.  
  
> [!NOTE]
>  `ThrowError` предназначены для использования только с точки зрения возврат из-за ошибки в свойство Get или Set функцию или метод автоматизации. Это только представляют время, которые будут подходящего обработчика исключений в стеке.  
  
 Существуют вспомогательные функции для наиболее частых предопределенные `SCODE`s, таких как [COleControl::SetNotSupported](../mfc/reference/colecontrol-class.md#setnotsupported), [COleControl::GetNotSupported](../mfc/reference/colecontrol-class.md#getnotsupported), и [COleControl:: SetNotPermitted](../mfc/reference/colecontrol-class.md#setnotpermitted).  
  
 Список предварительно определенных `SCODE`s и инструкции по определению пользовательских `SCODE`s, см. в разделе [обработка ошибок в свой элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX: Дополнительные разделы.  
  
 Дополнительные сведения об отчетности исключения в другие области кода см. в разделе [COleControl::FireError](../mfc/reference/colecontrol-class.md#fireerror) и разделе [обработка ошибок в свой элемент управления ActiveX](../mfc/mfc-activex-controls-advanced-topics.md) в элементах управления ActiveX: Дополнительные разделы.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

