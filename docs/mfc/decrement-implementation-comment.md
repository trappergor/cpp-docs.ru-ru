---
title: "--/ / Комментарий реализации | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Implementation comment in MFC source files
- comments, MFC
- MFC source files, Implementation comment
- comments, Implementation comments
ms.assetid: 4d799c07-8e71-4a6b-90ab-8282d6ff48ce
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 437b091b2237c7219a0afeee46d78164751e6d3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="-implementation-comment"></a>// Комментарий реализации
`// Implementation` Раздел является наиболее важной частью объявления любого класса MFC.  
  
 Этот раздел содержит все сведения о реализации. Переменные-члены и функции-члены могут отображаться в этом разделе. Все ниже этой линии могут изменяться в будущих выпусков платформы MFC. Если ее не избежать, не следует полагаться на следующие сведения о `// Implementation` строки. Кроме того члены, объявленные под линией реализации не документируются, несмотря на то, что некоторые реализации рассматривается в Технические примечания. В этом разделе, независимо от того, какой раздел функции базового класса определено, так как тот факт, что функция переопределяет реализацию базового класса считается реализации находиться переопределения виртуальных функций в базовом классе. Как правило, эти члены, защищены, но не всегда.  
  
 Обратите внимание, из `CStdioFile` со списком под [пример комментариев](../mfc/an-example-of-the-comments.md) члены, объявленные ниже `// Implementation` комментарий может быть объявлен как **открытый**, `protected`, или `private`. Эти элементы только следует использовать с осторожностью, поскольку может измениться в будущем. Объявление группы элементов как **открытый** может оказаться необходимым для реализации библиотеки классов для правильной работы. Однако это не означает, что можно безопасно использовать члены, объявленные таким образом.  
  
> [!NOTE]
>  Возможно, вам комментарии из оставшихся типов выше или ниже `// Implementation` комментарий. В любом случае они описываются виды членов, объявленных под ними. Если они встречаются ниже `// Implementation` комментарий, предполагается, что элементы могут измениться в будущих версиях для MFC.  
  
## <a name="see-also"></a>См. также  
 [С помощью исходные файлы MFC](../mfc/using-the-mfc-source-files.md)   
 [Пример комментариев](../mfc/an-example-of-the-comments.md)   
 [/ / Комментарий конструкторов](../mfc/decrement-constructors-comment.md)   
 [/ / Комментарий атрибутов](../mfc/decrement-attributes-comment.md)   
 [/ / Комментарий операций](../mfc/decrement-operations-comment.md)   
 [Комментарий Переопределяемости](../mfc/decrement-overridables-comment.md)

