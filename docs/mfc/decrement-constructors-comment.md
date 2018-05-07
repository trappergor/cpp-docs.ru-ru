---
title: --/ / Комментарий конструкторов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors comment
- declarations, constructors
- MFC source files, Constructors comment
- declaring constructors, code comments
- comments, MFC
- comments, constructors comment
- constructors [MFC], declaring
- instance constructors, code comments
ms.assetid: f400774e-ba85-49ed-85b7-70ef2f7dcb2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71b78e74b4b8d974fceaf5f854c9890cd7cdd1a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="-constructors-comment"></a>// Комментарий конструкторов
`// Constructors` Раздел объявления класса MFC объявляет конструкторы (в том смысле, C++), а также все функции инициализации, необходимые для действительно использовать объект. Например `CWnd::Create` находится в разделе конструкторы, так как перед использованием `CWnd` объекта, он должен быть «полностью создан», сначала вызов конструктора C++ и последующего вызова **создать** функции. Как правило эти члены являются открытыми.  
  
 Например, класс `CStdioFile` имеет три конструктора, один из которых отображается в списке под [пример комментариев](../mfc/an-example-of-the-comments.md).  
  
## <a name="see-also"></a>См. также  
 [С помощью исходные файлы MFC](../mfc/using-the-mfc-source-files.md)   
 [/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)   
 [/ / Комментарий атрибутов](../mfc/decrement-attributes-comment.md)   
 [/ / Комментарий операций](../mfc/decrement-operations-comment.md)   
 [Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

