---
title: --Комментарий конструкторов
ms.date: 11/04/2016
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
ms.openlocfilehash: ee36ad991f2a19211b494010d6ff0a5338b80557
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50480708"
---
# <a name="-constructors-comment"></a>// Комментарий конструкторов

`// Constructors` Разделе объявления класса MFC объявляется конструкторы (в том смысле, C++), а также любые функции инициализации, необходимые для действительно использовать объект. Например `CWnd::Create` находится в разделе конструкторов, так как раньше использовалась `CWnd` объекта, он должен «полностью создаваться», сначала вызова конструктора по C++ и затем вызвав `Create` функции. Как правило эти члены являются открытыми.

Например, класс `CStdioFile` содержит три конструктора, один из которых отображается в списке под [пример комментариев](../mfc/an-example-of-the-comments.md).

## <a name="see-also"></a>См. также

[Использование файлов с исходным кодом MFC](../mfc/using-the-mfc-source-files.md)<br/>
[/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)<br/>
[/ / Комментарий атрибутов](../mfc/decrement-attributes-comment.md)<br/>
[/ / Комментарий операций](../mfc/decrement-operations-comment.md)<br/>
[/ / Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

