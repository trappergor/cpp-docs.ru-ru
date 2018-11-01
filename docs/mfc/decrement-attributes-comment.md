---
title: --Комментарий атрибутов
ms.date: 11/04/2016
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
ms.openlocfilehash: 33ee18400e03b55a26c4ad17e8d1ba6853ccda88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486077"
---
# <a name="-attributes-comment"></a>// Комментарий атрибутов

`// Attributes` Раздел объявление класса MFC содержит открытый атрибуты (или свойств) объекта. Обычно это переменных-членов или функций Get и Set. Функции «Get» и «Set» может или не могут быть виртуальными. Функции «Get» обычно являются **const**, так как в большинстве случаев они не имеют побочных эффектов. Эти члены являются открытыми обычным образом; защищенные и закрытые атрибуты обычно находятся в разделе «Реализация».

В примере со списком из класса `CStdioFile`в разделе [пример комментариев](../mfc/an-example-of-the-comments.md), список содержит одну переменную-член, *m_pStream*. Класс `CDC` перечислены приблизительно 20 элементов в разделе этого комментария.

> [!NOTE]
>  Крупный классов, таких как `CDC` и `CWnd`, могут иметь так много элементы, которые просто перечислении всех атрибутов в одной группе могут быть практически для ясности. В таких случаях библиотека классов использует другие комментарии как заголовки для дальнейшего разделения членов. Например `CDC` использует `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`и многое другое. Группы, представляющие атрибуты последует обычного синтаксиса, описанного выше. Многие классы OLE имеют реализации раздел с именем `// Interface Maps`.

## <a name="see-also"></a>См. также

[Использование файлов с исходным кодом MFC](../mfc/using-the-mfc-source-files.md)<br/>
[Пример комментариев](../mfc/an-example-of-the-comments.md)<br/>
[/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)<br/>
[/ / Комментарий конструкторов](../mfc/decrement-constructors-comment.md)<br/>
[/ / Комментарий операций](../mfc/decrement-operations-comment.md)<br/>
[/ / Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

