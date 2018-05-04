---
title: Составные операторы (блоки) | Документы Microsoft
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
ms.openlocfilehash: 9a8823935ee2f871cdc033aec23f05fc108244e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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