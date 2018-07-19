---
title: Определение макроса NMAKE | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- macros, NMAKE
- defining NMAKE macros
- NMAKE macros, defining
ms.assetid: 45aae451-9d33-4a3d-8799-2e0cae17070d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5997eee052ebba198e1fb52da35322c65a32627b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367138"
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