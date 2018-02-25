---
title: "&lt;ccomplex&gt; | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <ccomplex>
dev_langs:
- C++
ms.assetid: a9fcb5f0-88e3-464b-a5fd-d1afb8cd7e6f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eb279929a460c43bb7ca564615fde494e3a0eb99
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="ltccomplexgt"></a>&lt;ccomplex&gt;
Включает заголовок стандартной библиотеки C++ [\<complex>](../standard-library/complex.md), который эффективно включает заголовок \<complex.h> стандартной библиотеки C и добавляет связанные имена в пространство имен `std`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
#include <ccomplex>  
  
```  
  
## <a name="remarks"></a>Примечания  
 Включение этого заголовка гарантирует, что имена, объявленные с помощью внешней компоновки в заголовке стандартной библиотеки C, объявляются в пространстве имен `std`.  
  
 Имя `clog`, которое объявлено в \<complex.h>, не определено в пространстве имен `std` из-за возможных конфликтов с `clog`, объявленным в [\<iostream>](../standard-library/iostream.md).  
  
## <a name="see-also"></a>См. также  
 [Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)   
 [Общие сведения о стандартной библиотеке C++](../standard-library/cpp-standard-library-overview.md)



