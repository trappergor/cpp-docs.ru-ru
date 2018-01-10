---
title: "Определение макроса NMAKE | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96799bbd10d442c50d66ac4e84169864b9b989ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="defining-an-nmake-macro"></a>Определение макроса NMAKE
## <a name="syntax"></a>Синтаксис  
  
```  
  
macroname=string  
```  
  
## <a name="remarks"></a>Примечания  
 *Имя макроса* представляет собой сочетание букв, цифр и символы подчеркивания (_), не более 1 024 символов и учитывается регистр. *Имя макроса* может содержать вызванный макрос. Если *имя макроса* состоит только из вызванного макроса, вызываемый макрос не может быть пустым или равным NULL.  
  
 `string` Может быть любая последовательность из нуля или более символов. Пустая строка содержит ноль знаков или только пробелы или знаки табуляции. `string` Может содержать вызов макроса.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Специальные символы в макросах](../build/special-characters-in-macros.md)  
  
 [Пустой и неопределенный макрос](../build/null-and-undefined-macros.md)  
  
 [Где следует определять макросы](../build/where-to-define-macros.md)  
  
 [Приоритет в макроопределениях](../build/precedence-in-macro-definitions.md)  
  
## <a name="see-also"></a>См. также  
 [Макросы и программа NMAKE](../build/macros-and-nmake.md)