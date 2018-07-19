---
title: --Атрибуты комментарий | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44b34c2e2d22d0a0a2feb15f6bf2793b68dc7042
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929573"
---
# <a name="-attributes-comment"></a>// Комментарий атрибутов
`// Attributes` Раздел объявления класса MFC содержит открытые атрибуты (или свойств) объекта. Обычно это переменных-членов или функций Get и Set. Функции «Get» и «Set» может или не могут быть виртуальными. Функции «Get» обычно являются **const**, так как в большинстве случаев они не имеют побочных эффектов. Эти члены являются открытыми обычным образом; защищенные и закрытые атрибуты обычно находятся в разделе реализации.  
  
 В образце вывод из класса `CStdioFile`в разделе [пример комментариев](../mfc/an-example-of-the-comments.md), список включает одну переменную-член, *m_pStream*. Класс `CDC` перечислены приблизительно 20 элементов в группе этого комментария.  
  
> [!NOTE]
>  Крупный классов, таких как `CDC` и `CWnd`, может содержать так много члены, которые просто перечисление всех атрибутов в одну группу могут быть значительно большей ясности. В таких случаях библиотека классов использует другие примечания как заголовки для дальнейшего разделения элементов. Например `CDC` использует `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`и многое другое. Группы, представляющие атрибутов будет следовать обычный синтаксис, описанный выше. Многие классы OLE имеют реализации раздел с именем `// Interface Maps`.  
  
## <a name="see-also"></a>См. также  
 [С помощью исходные файлы MFC](../mfc/using-the-mfc-source-files.md)   
 [Пример комментариев](../mfc/an-example-of-the-comments.md)   
 [/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)   
 [/ / Комментарий конструкторов](../mfc/decrement-constructors-comment.md)   
 [/ / Комментарий операций](../mfc/decrement-operations-comment.md)   
 [Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

