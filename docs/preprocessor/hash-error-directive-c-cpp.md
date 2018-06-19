---
title: '#Ошибка директивы (C/C++) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba4f0e06798bc6419f8db0471f19588039eb679a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33905576"
---
# <a name="error-directive-cc"></a>Директива #error (C/C++)
Директива `#error` создает заданное пользователем сообщение об ошибке во время компиляции, а затем завершает компиляцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>Примечания  
 Эта директива выдает сообщение об ошибке включает *строке токена* параметра. Параметр `token-string` не подлежит расширению макроса. Эта директива наиболее полезна в ходе предварительной обработки и позволяет уведомлять разработчика о противоречиях в программе или о нарушении ограничений. В следующем примере демонстрируется обработка ошибки во время предварительной обработки.  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>См. также  
 [Директивы препроцессора](../preprocessor/preprocessor-directives.md)