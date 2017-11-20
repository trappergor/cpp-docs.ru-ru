---
title: "Составные операторы (блоки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs: C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c9fc47721ba5cecc8ca9f61f89ecedebaed18ae4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compound-statements-blocks"></a>Составные операторы (блоки)
Составной оператор состоит из нуля или более операторов, заключенный в фигурные скобки (**{}**). Составной оператор может использоваться везде, где ожидается оператор. Составные инструкции часто называются "блоками".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Примечания  
 В следующем примере используется составной оператор как *инструкции* частью **Если** инструкции (в разделе [if инструкции](../cpp/if-else-statement-cpp.md) подробные сведения о синтаксисе):  
  
```  
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
{
    Balance -= Amount;  
}
```  
  
> [!NOTE]
>  Поскольку объявление является инструкцией, может быть одной из инструкций в *списка операторов*. Таким образом, имена, которые были объявлены в составном операторе, но не были явно объявлены как статичные, имеют локальную область видимости, а объекты — еще и локальное время существования. В разделе [область](../cpp/scope-visual-cpp.md) для получения сведений об именах с локальной областью действия.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)