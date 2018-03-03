---
title: "-DYNAMICBASE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 07fd3c89cb2cff1fed06189ac66b2e67f7e52ade
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dynamicbase"></a>/DYNAMICBASE
Указывает, можно ли случайным образом переместить исполняемый образ во время загрузки с помощью технологии ASLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию компоновщик устанавливает **/DYNAMICBASE** параметр.  
  
 Этот параметр изменяет заголовок исполняемого образа, чтобы указать, может ли загрузчик случайным образом переместить образ во время загрузки.  
  
 ASLR поддерживается в Windows Vista, Windows Server 2008, Windows 7, Windows 8 и Windows Server 2012.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [Способы защиты независимого Поставщика программного обеспечения Windows](http://msdn.microsoft.com/library/bb430720.aspx)