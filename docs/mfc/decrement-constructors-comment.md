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
ms.openlocfilehash: f58c8410de51a4692dd0e7f018d40eaa28c0dae8
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929586"
---
# <a name="-constructors-comment"></a>// Комментарий конструкторов
`// Constructors` Раздел объявления класса MFC объявляет конструкторы (в том смысле, C++), а также все функции инициализации, необходимые для действительно использовать объект. Например `CWnd::Create` находится в разделе конструкторы, так как перед использованием `CWnd` объекта, он должен быть «полностью создан», сначала вызов конструктора C++ и последующего вызова `Create` функции. Как правило эти члены являются открытыми.  
  
 Например, класс `CStdioFile` имеет три конструктора, один из которых отображается в списке под [пример комментариев](../mfc/an-example-of-the-comments.md).  
  
## <a name="see-also"></a>См. также  
 [С помощью исходные файлы MFC](../mfc/using-the-mfc-source-files.md)   
 [/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)   
 [/ / Комментарий атрибутов](../mfc/decrement-attributes-comment.md)   
 [/ / Комментарий операций](../mfc/decrement-operations-comment.md)   
 [Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

