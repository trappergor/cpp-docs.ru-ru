---
title: --Комментарий Переопределяемости | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Overridables comment in MFC source files
- MFC source files, Overridables comment
- overriding, Overridables comment in MFC source files
- comments, MFC
ms.assetid: 8968dea5-0d94-451f-bcb2-991580e65ba2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d50fb62767f2130e89cb75df5d66f8c18ce2a097
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428061"
---
# <a name="-overridables-comment"></a>// Комментарий переопределяемости

`// Overridables` Раздел объявление класса MFC содержит виртуальных функций, которые можно переопределить в производном классе, когда необходимо изменить поведение базового класса. Они обычно называются начиная с «On», несмотря на то, что это не является обязательным. Здесь функции предназначены для переопределяться и зачастую реализуются или какую-либо «callback» или «подключить». Как правило эти члены будут защищены.

В MFC чистые виртуальные функции, всегда размещаются в этом разделе. Чистой виртуальной функции в C++ является одним из формы:

`virtual void OnDraw( ) = 0;`

В примере со списком из класса `CStdioFile`в [пример комментариев](../mfc/an-example-of-the-comments.md), список включает раздел не переопределяются. Класс `CDocument`, с другой стороны, перечислены приблизительно 10 функции является переопределяемым элементом.

В некоторых классах, может также появиться комментарий `// Advanced Overridables`. Имеются функции, которые только опытным программистам следует пытаться переопределить. Возможно, никогда не требуется переопределять их.

> [!NOTE]
>  Соглашений, описываемых в этой статье также работает хорошо, как правило, для автоматизация (ранее известная как OLE-автоматизация) методы и свойства. Методы автоматизации похожи на операции MFC. Свойства автоматизации похожи на атрибуты MFC. События модели автоматизации (поддерживается для элементов управления ActiveX, ранее известные как элементы управления OLE) похожи на функции MFC является переопределяемым элементом.

## <a name="see-also"></a>См. также

[Использование файлов с исходным кодом MFC](../mfc/using-the-mfc-source-files.md)<br/>
[Пример комментариев](../mfc/an-example-of-the-comments.md)<br/>
[/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)<br/>
[/ / Комментарий конструкторов](../mfc/decrement-constructors-comment.md)<br/>
[/ / Комментарий атрибутов](../mfc/decrement-attributes-comment.md)<br/>
[/ / Комментарий операций](../mfc/decrement-operations-comment.md)

