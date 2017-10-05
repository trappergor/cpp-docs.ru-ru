---
title: "Составные операторы (блоки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 9dc28fde0ab2cf5b21771347554d0c664b7f462d
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

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
