---
title: -HIGHENTROPYVA | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /HIGHENTROPYVA
dev_langs:
- C++
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 122f524db9af10449ce809e5a8de78148d04d431
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="highentropyva"></a>/HIGHENTROPYVA
Указывает, поддерживает ли исполняемый образ 64-разрядную технологию ASLR с высокой энтропией.  
  
```  
  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр изменяет заголовок DLL- или EXE-файла, указывая, поддерживается ли ASLR с 64-разрядными адресами. Если для исполняемого файла и всех модулей, от которых он зависит, задан этот параметр, то операционная система, поддерживающая 64-разрядную технологию, может переместить сегменты исполняемого образа во время загрузки, используя случайные адреса в 64-разрядном виртуальном адресном пространстве. Благодаря обширному адресному пространству злоумышленнику будет труднее догадаться о расположении определенной области в памяти.  
  
 По умолчанию компоновщик устанавливает этот параметр для 64-разрядных исполняемых образов. Установка данного параметра [/DYNAMICBASE](../../build/reference/dynamicbase.md) параметр также должен быть установлен.  
  
## <a name="see-also"></a>См. также  
 [Параметры EDITBIN](../../build/reference/editbin-options.md)   
 [/ DYNAMICBASE](../../build/reference/dynamicbase.md)   
 [Способы защиты независимого Поставщика программного обеспечения Windows](http://msdn.microsoft.com/library/bb430720.aspx)