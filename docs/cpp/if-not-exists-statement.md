---
title: оператор __if_not_exists | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd4e586a211d7c4e2ead1ce3f225e2d92d2bd5a7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418820"
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