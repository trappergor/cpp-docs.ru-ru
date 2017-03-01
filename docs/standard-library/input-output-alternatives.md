---
title: "Альтернативные варианты ввода и вывода | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
caps.latest.revision: 8
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 45cec9f7c4c45ef12c7d22a7c3c311f7ce3f4cb5
ms.lasthandoff: 02/24/2017

---
# <a name="inputoutput-alternatives"></a>Альтернативные варианты ввода и вывода
Visual C++ предоставляет несколько альтернатив для программирования ввода-вывода:  
  
-   Прямой ввод-вывод без буферизации на основе библиотеки времени выполнения С.  
  
-   Потоковый ввод-вывод на основе библиотеки времени выполнения ANSI C.  
  
-   Прямой ввод-вывод на консоль и в порт.  
  
-   Библиотека MFC.  
  
-   Стандартная библиотека Microsoft C++.  
  
 Классы iostream полезны для ввода-вывода форматированного текста с буферизацией. Они также могут использоваться для ввода-вывода без буферизации или двоичного ввода-вывода, если требуется интерфейс программирования C++ и принято решение отказаться от использования библиотеки Microsoft Foundation Class (MFC). Классы iostream — это объектно-ориентированная альтернатива вводу-выводу с помощью функций времени выполнения С.  
  
 Классы iostream можно использовать с операционной системой Microsoft Windows. Потоки строк и файлов работают без ограничений, но объекты потока символьного режима `cin`, `cout`, `cerr`, и `clog` не совместимы с графическим интерфейсом пользователя Windows. Также можно получать производные пользовательские классы потоков, которые взаимодействуют непосредственно со средой Windows.  
  
## <a name="see-also"></a>См. также  
 [Что такое поток](../standard-library/what-a-stream-is.md)


