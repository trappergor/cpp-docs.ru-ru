---
title: "оператор __if_not_exists | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __if_not_exists
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
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
ms.openlocfilehash: 5eff74bd6405d7ec63b3cc8fbea968df984fddb8
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="ifnotexists-statement"></a>Оператор __if_not_exists
Оператор `__if_not_exists` проверяет, существует ли указанный идентификатор. Если идентификатор не существует, выполняется определенный блок операторов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Параметры  
  
|Параметр|Описание|  
|---------------|-----------------|  
|`identifier`|Идентификатор, наличие которого требуется проверить.|  
|`statements`|Один или несколько операторов для выполнения, если `identifier` не существует.|  
  
## <a name="remarks"></a>Примечания  
  
> [!CAUTION]
>  Для получения самых надежных результатов используйте оператор `__if_not_exists` при следующих ограничениях.  
  
-   Применяйте оператор `__if_not_exists` только к простым типам, а не шаблонам.  
  
-   Применяйте оператор `__if_not_exists` к идентификаторам как внутри, так и вне класса. Не применяйте оператор `__if_not_exists` к локальным переменным.  
  
-   Используйте оператор `__if_not_exists` только в теле функции. За пределами тела функции оператор `__if_not_exists` может проверять только полностью определенные типы.  
  
-   При проверке перегруженных функций невозможно выполнить проверку определенной формы перегрузки.  
  
 Дополнением к `__if_not_exists` инструкция является [__if_exists](../cpp/if-exists-statement.md) инструкции.  
  
## <a name="example"></a>Пример  
 Например, об использовании `__if_not_exists`, см. [__if_exists инструкции](../cpp/if-exists-statement.md).  
  
## <a name="see-also"></a>См. также  
 [Операторы выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова](../cpp/keywords-cpp.md)   
 [Оператор __if_exists](../cpp/if-exists-statement.md)
