---
title: "Справочник (C++ AMP) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::Reference (C++ AMP)
dev_langs:
- C++
helpviewer_keywords:
- C++ Accelerated Massive Parallelism, reference
ms.assetid: 372a8aed-8a53-48c9-996f-9c3cf09c9fa8
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: cc654cedd8639377ab7011c91454f1508c730247
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="reference-c-amp"></a>Справочник (C++ AMP)
В этом разделе содержатся справочные сведения для среды выполнения C++ Accelerated Massive Parallelism (C++ AMP).  
  
> [!NOTE]
>  В стандарте языка C++ использование идентификаторов, начинающихся с символа подчеркивания (`_`), зарезервировано для таких реализаций, как библиотеки. Не используйте в коде имена, начинающиеся с символа подчеркивания. Поведение элементов кода, имена которых соответствуют этому соглашению, не гарантируется и может быть изменено в будущем. По этим причинам такие элементы кода исключены из этой документации.  
  
## <a name="in-this-section"></a>Содержание  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)  
 Предоставляет классы и функции, позволяющие ускорение кода C++ в данных параллельного оборудования.  
  
 [Пространство имен Concurrency::Direct3D](concurrency-direct3d-namespace.md)  
 Предоставляет функции, поддерживающие взаимодействие D3D. Обеспечивает эффективное использование ресурсов D3D для вычислений в коде AMP и использование ресурсов, созданные в AMP в коде D3D, без создания промежуточных резервированием. Можно использовать C++ AMP постепенно ускорения вычислений разделы приложений DirectX и использовать D3D API на данные, полученные из AMP вычислений.  
  
 [Пространство имен Concurrency::fast_math](concurrency-fast-math-namespace.md)  
 Функции в `fast_math` пространства имен не совместимы с C99. Имеются только одиночной точности версии каждой функции. Эти функции используют встроенные функции DirectX, которые работают быстрее, чем соответствующие функции в `precise_math` пространства имен и расширенная поддержка двойной точности на сочетания клавиш не требуется, но они являются менее точными. Существуют две версии каждой функции для источника уровня совместимости с кодом C99; обе версии принимают и возвращают значения одинарной точности.  
  
 [Пространство имен Concurrency::Graphics](concurrency-graphics-namespace.md)  
 Предоставляет типы и функции, предназначенные для программирования графики.  
  
 [Пространство имен Concurrency::precise_math](concurrency-precise-math-namespace.md)  
 Функции в `precise_math` пространства имен являются совместимыми C99. Включены одиночной точности и двойной точности версии каждой функции. Эти функции, включая функции одиночной точности — требуется расширенная поддержка двойной точности на сочетания клавиш.  
  
## <a name="related-sections"></a>Связанные разделы  
 [C++ AMP (C++ Accelerated Massive Parallelism)](../../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)  
 C++ AMP ускоряют выполнение кода C++, используя преимущества данных параллельного оборудования, обычно присутствует в качестве графического процессора (GPU) на выделенной видеокарте.






