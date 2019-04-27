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
ms.openlocfilehash: e0d02af016a0c7bfb0869b7cdd30fe0db2975102
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62240865"
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
