---
title: Составные операторы (блоки) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c85de0f147d0cfed873a091d17c46e56bf5758a9
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408799"
---
# <a name="compound-statements-blocks"></a>Составные операторы (блоки)
Составной оператор состоит из нуля или более операторов, заключенных в фигурные скобки (**{}**). Составной оператор может использоваться везде, где ожидается оператор. Составные инструкции часто называются "блоками".  
  
## <a name="syntax"></a>Синтаксис  
  
```  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Примечания  
 В следующем примере используется составной оператор как *инструкции* частью **Если** инструкция (см. в разделе [if инструкции](../cpp/if-else-statement-cpp.md) Дополнительные сведения о синтаксисе):  
  
```cpp 
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
>  Поскольку объявление является инструкцией, объявление может представлять собой один из операторов в *списка операторов*. Таким образом, имена, которые были объявлены в составном операторе, но не были явно объявлены как статичные, имеют локальную область видимости, а объекты — еще и локальное время существования. См. в разделе [область](../cpp/scope-visual-cpp.md) Дополнительные сведения об именах с локальной областью.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения об операторах в C++](../cpp/overview-of-cpp-statements.md)