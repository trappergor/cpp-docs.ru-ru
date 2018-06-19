---
title: --Комментарий Переопределяемости | Документы Microsoft
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
ms.openlocfilehash: 1b71d61175e5446ac33dd0ff6a011d06f601b5a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345392"
---
# <a name="-overridables-comment"></a>// Комментарий переопределяемости
`// Overridables` Раздел объявления класса MFC содержит виртуальных функций, которые можно переопределить в производном классе, если необходимо изменить поведение базового класса. Они обычно называются начиная с «On», несмотря на то, что он не является обязательным. Здесь функции предназначены для переопределяться и зачастую реализуются или какой-то «callback» или «подключить». Как правило эти члены являются защищенными.  
  
 В MFC чистые виртуальные функции всегда размещаются в этом разделе. Чистой виртуальной функции в C++ является одним из формы:  
  
 `virtual void OnDraw( ) = 0;`  
  
 В образце вывод из класса `CStdioFile`в [пример комментариев](../mfc/an-example-of-the-comments.md), список содержит раздел отсутствует переопределяемости. Класс **CDocument**, с другой стороны, перечислены приблизительно 10 переопределяемый член функции.  
  
 В некоторых классах, также могут возникать комментарий `// Advanced Overridables`. Имеются функции, которые только опытным программистам должен пытаться переопределить. Вероятно, никогда не потребуется для их переопределения.  
  
> [!NOTE]
>  Соглашения, описанные в этой статье также работают, как правило, для автоматизация (ранее известная как OLE-автоматизация) методы и свойства. Методы автоматизации похожи на операции MFC. Свойства модели автоматизации аналогичны атрибуты MFC. События модели автоматизации (поддерживается для элементов управления ActiveX, ранее известные как элементы управления OLE) аналогичны функциям переопределяемый член MFC.  
  
## <a name="see-also"></a>См. также  
 [С помощью исходные файлы MFC](../mfc/using-the-mfc-source-files.md)   
 [Пример комментариев](../mfc/an-example-of-the-comments.md)   
 [/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)   
 [/ / Комментарий конструкторов](../mfc/decrement-constructors-comment.md)   
 [/ / Комментарий атрибутов](../mfc/decrement-attributes-comment.md)   
 [/ / Комментарий операций](../mfc/decrement-operations-comment.md)

