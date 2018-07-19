---
title: Ошибка вычислителя выражений CXX0033 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0033
dev_langs:
- C++
helpviewer_keywords:
- CAN0033
- CXX0033
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 720b1aec6c9be16879119bc0e8148a301507577a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299504"
---
# <a name="expression-evaluator-error-cxx0033"></a>Ошибка вычислителя выражений CXX0033
Ошибка в данных типа OMF  
  
 Исполняемый файл не содержал формат модуля допустимый объект (OMF) для отладки.  
  
 Эта ошибка идентична CAN0033.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Исполняемый файл не был создан с компоновщик, выпущенный в этой версии Visual C++. Повторно связать объектный код при помощи текущей версии программы LINK.exe.  
  
2.  Возможно, что поврежден файл .exe. Перекомпилируйте и осуществлять перекомпоновку программы.