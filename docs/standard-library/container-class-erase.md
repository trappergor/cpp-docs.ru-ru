---
title: "Класс контейнера::erase | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "erase - метод"
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Класс контейнера::erase
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  В этом разделе в документации Visual C\+\+ как нефункциональный пример контейнеров, используемых в стандартной библиотеке C\+\+.  Дополнительные сведения см. в разделе [Контейнеров STL](../standard-library/stl-containers.md).  
  
 Удаляет элемент.  
  
## Синтаксис  
  
```  
  
      iterator erase(  
   iterator _Where   
);  
iterator erase(  
   iterator _First,  
   iterator _Last   
);  
```  
  
## Заметки  
 Первый функцию\-член удаляет элемент контролируемой последовательности, указанное в \_Where **.** Второй функцию\-член удаляет элементы контролируемой последовательности в диапазоне \[`_First`, `_Last`\).  Оба возвращал итератор, обозначает первый элемент оставшиеся за всеми удаленными элементами или [end](../Topic/Container%20Class::end.md), если такой элемент не существует.  
  
 Функции\-члены вызывает исключение, только если операция копирования создает исключение.  
  
## См. также  
 [Пример класса контейнера](../Topic/Sample%20Container%20Class.md)