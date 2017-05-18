---
title: "Что такое поток | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 75c23582cbbb42a417a7a5effdb879300c2a7732
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="what-a-stream-is"></a>Что такое поток
Как и C, в C++ нет встроенных потоков ввода-вывода. Однако в состав всех компиляторов C++ входит системный объектно ориентированный пакет ввода-вывода — классы iostream. Центральной концепцией классов iostream является поток. Можно считать, что поток — это смарт-файл, который выступает в качестве источника и назначения для байт. Характеристики потока определяется его классом и пользовательскими операторами вставки и извлечения.  
  
 С помощью драйверов устройств дисковая операционная система взаимодействует с клавиатурой, монитором, принтером и портами ввода-вывода как с расширенными файлами. Классы iostream взаимодействуют с этими расширенными файлами. Встроенные классы поддерживают чтение из памяти и запись в память, причем синтаксис этих операций идентичен синтаксису для операций дискового ввода-вывода, что позволяет легко создавать производные классы потока.  
  
## <a name="in-this-section"></a>Содержание  
 [Альтернативные варианты ввода-вывода](../standard-library/input-output-alternatives.md)  
  
## <a name="see-also"></a>См. также  
 [Программирование iostream](../standard-library/iostream-programming.md)


