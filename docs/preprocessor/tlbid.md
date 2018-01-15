---
title: "TLBID | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: tlbid
dev_langs: C++
helpviewer_keywords: tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 812b105fc02782b611b3f55061e448062dcd07c7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="tlbid"></a>tlbid
**Конкретных C++**  
  
 Позволяет загружать библиотеки, отличные от основной библиотеки типов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
tlbid(number)  
```  
  
#### <a name="parameters"></a>Параметры  
 `number`  
 Номер библиотеки типов в файле с именем `filename`.  
  
## <a name="remarks"></a>Примечания  
 Если в одну библиотеку DLL встроено несколько библиотек типов, с помощью `tlbid` можно загружать библиотеки, отличные от основной библиотеки типов.  
  
 Пример:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 эквивалентно выражению:  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **КОНЕЦ определенного C++**  
  
## <a name="see-also"></a>См. также  
 [атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)   
 [директива #import](../preprocessor/hash-import-directive-cpp.md)