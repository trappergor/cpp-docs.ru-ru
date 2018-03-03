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
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2342354528811f415a9c9aeb819e2c0e7cec6646
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
|Параметр|Описание:|  
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