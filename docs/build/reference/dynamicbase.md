---
title: -DYNAMICBASE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /dynamicbase
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE editbin option
- DYNAMICBASE editbin option
- /DYNAMICBASE editbin option
ms.assetid: edb3df90-7b07-42fb-a94a-f5a4c1d325d6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d7a4cf7aa35d7ad6b41fc6d61f3f27662ae2c8d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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