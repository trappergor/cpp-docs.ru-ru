---
title: "Что такое поток | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], iostream programming
- data [C++], reading
- streams [C++], in iostream classes
- streams [C++]
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7515c587a651b31bce7f3d1c56777a2a908c488a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="what-a-stream-is"></a>Что такое поток
Как и C, в C++ нет встроенных потоков ввода-вывода. Однако в состав всех компиляторов C++ входит системный объектно ориентированный пакет ввода-вывода — классы iostream. Центральной концепцией классов iostream является поток. Можно считать, что поток — это смарт-файл, который выступает в качестве источника и назначения для байт. Характеристики потока определяется его классом и пользовательскими операторами вставки и извлечения.  
  
 С помощью драйверов устройств дисковая операционная система взаимодействует с клавиатурой, монитором, принтером и портами ввода-вывода как с расширенными файлами. Классы iostream взаимодействуют с этими расширенными файлами. Встроенные классы поддерживают чтение из памяти и запись в память, причем синтаксис этих операций идентичен синтаксису для операций дискового ввода-вывода, что позволяет легко создавать производные классы потока.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Альтернативные варианты ввода-вывода](../standard-library/input-output-alternatives.md)  
  
## <a name="see-also"></a>См. также  
 [Программирование iostream](../standard-library/iostream-programming.md)

