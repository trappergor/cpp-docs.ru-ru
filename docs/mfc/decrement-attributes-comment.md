---
title: "--Атрибуты комментарий | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- comments, Attributes
- Attributes comment in MFC source files
- MFC source files, Attributes comment
- public attributes comment
ms.assetid: 96388e11-42df-4994-aedf-decd152961a7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 18a142cc0434e0e09e69d9bffc30826c461cf185
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="-attributes-comment"></a>// Комментарий атрибутов
`// Attributes` Раздел объявления класса MFC содержит открытые атрибуты (или свойств) объекта. Обычно это переменных-членов или функций Get и Set. Функции «Get» и «Set» может или не могут быть виртуальными. Функции «Get» обычно являются **const**, так как в большинстве случаев они не имеют побочных эффектов. Эти члены являются открытыми обычным образом; защищенные и закрытые атрибуты обычно находятся в разделе реализации.  
  
 В образце вывод из класса `CStdioFile`в разделе [пример комментариев](../mfc/an-example-of-the-comments.md), список включает одну переменную-член, `m_pStream`. Класс `CDC` перечислены приблизительно 20 элементов в группе этого комментария.  
  
> [!NOTE]
>  Крупный классов, таких как `CDC` и `CWnd`, может содержать так много члены, которые просто перечисление всех атрибутов в одну группу могут быть значительно большей ясности. В таких случаях библиотека классов использует другие примечания как заголовки для дальнейшего разделения элементов. Например `CDC` использует `// Device-Context Functions`, `// Drawing Tool Functions`, `// Drawing Attribute Functions`и многое другое. Группы, представляющие атрибутов будет следовать обычный синтаксис, описанный выше. Многие классы OLE имеют реализации раздел с именем `// Interface Maps`.  
  
## <a name="see-also"></a>См. также  
 [С помощью исходные файлы MFC](../mfc/using-the-mfc-source-files.md)   
 [Пример комментариев](../mfc/an-example-of-the-comments.md)   
 [/ / Комментарий реализации](../mfc/decrement-implementation-comment.md)   
 [/ / Комментарий конструкторов](../mfc/decrement-constructors-comment.md)   
 [/ / Комментарий операций](../mfc/decrement-operations-comment.md)   
 [Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

