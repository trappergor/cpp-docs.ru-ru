---
title: "Ошибка вычислителя выражений CXX0033 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: 6
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 3df60f5eed5a5018fd5dade69d10e1302db868f1
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0033"></a>Ошибка вычислителя выражений CXX0033
ошибка в данных типа OMF  
  
 Исполняемый файл не содержал формат допустимый объект модуля (OMF) для отладки.  
  
 Эта ошибка идентична CAN0033.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Исполняемый файл не был создан компоновщиком, выпущенным с этой версией Visual C++. Перекомпоновать объектный код при помощи текущей версии программы LINK.exe.  
  
2.  Файл .exe может быть повреждена. Повторная компиляция и осуществлять перекомпоновку программы.
