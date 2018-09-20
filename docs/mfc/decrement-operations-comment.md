---
title: --/ / Комментарий операций | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Operations comment in MFC source files
- comments, MFC
- MFC source files, Operations comments
ms.assetid: f3bff48d-26be-4db6-8435-9e4d079838c9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 73c4a7a70c9f2ed987337426793bd462c2a94309
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372500"
---
# <a name="-operations-comment"></a>// Комментарий операций

`// Operations` Раздел объявление класса MFC содержит функции-члены, которые можно вызвать для объекта, чтобы сделать его выполнять действия или действия (операции). Эти функции, обычно отличным от**const** так, как они обычно имеют побочные эффекты. Они могут быть виртуальными или невиртуальные в зависимости от потребностей класса. Как правило эти члены являются открытыми.

В примере со списком из класса `CStdioFile`в [пример комментариев](../mfc/an-example-of-the-comments.md), список включает две функции-члена в этот комментарий: `ReadString` и `WriteString`.

С помощью атрибутов, операций можно дополнительно разделить.

## <a name="see-also"></a>См. также

[Использование файлов с исходным кодом MFC](../mfc/using-the-mfc-source-files.md)<br/>
[Пример комментариев](../mfc/an-example-of-the-comments.md)<br/>
[/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)<br/>
[/ / Комментарий конструкторов](../mfc/decrement-constructors-comment.md)<br/>
[/ / Комментарий атрибутов](../mfc/decrement-attributes-comment.md)<br/>
[/ / Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

