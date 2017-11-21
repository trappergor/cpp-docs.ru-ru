---
title: "Ошибка вычислителя выражений CXX0033 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0033
dev_langs: C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 618dbe464adc64f36e35b9c329eb476166b8b5e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0033"></a>Ошибка вычислителя выражений CXX0033
Ошибка в данных типа OMF  
  
 Исполняемый файл не содержал формат модуля допустимый объект (OMF) для отладки.  
  
 Эта ошибка идентична CAN0033.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Исполняемый файл не был создан с компоновщик, выпущенный в этой версии Visual C++. Повторно связать объектный код при помощи текущей версии программы LINK.exe.  
  
2.  Возможно, что поврежден файл .exe. Перекомпилируйте и осуществлять перекомпоновку программы.