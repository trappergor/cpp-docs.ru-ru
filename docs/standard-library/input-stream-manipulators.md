---
title: "Манипуляторы входных потоков | Документы Майкрософт"
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
- input streams, manipulators
- input stream objects
ms.assetid: 0addcacb-7b7b-4d70-9775-a59abc400fb3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e92b41ee4140ff08bd6578ef79a1d297734ba870
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="input-stream-manipulators"></a>Манипуляторы входных потоков
Много манипуляторов, таких как [setprecision](../standard-library/iomanip-functions.md#setprecision), определенные для `ios` класса и таким образом применяются к входные потоки. Однако некоторые манипуляторы фактически влияют на объекты потока ввода. Наиболее важными из них являются манипуляторы основания системы счисления `dec`, `oct` и `hex`, которые определяют базу преобразования, используемую с числами из входного потока.  
  
 При извлечении манипулятор `hex` позволяет обрабатывать различные форматы входных данных. Например, c C, 0xc, 0xC, 0Xc и 0XC интерпретируются как десятичное целое число 12. Любой символ, отличный от цифр от 0 до 9, букв от A до F, букв от a до f, x и X, завершает числовое преобразование. Таким образом, последовательность `"124n5"` преобразуется в число 124 с заданными битом [basic_ios::fail](../standard-library/basic-ios-class.md#fail).  
  
## <a name="see-also"></a>См. также  
 [Потоки ввода](../standard-library/input-streams.md)

