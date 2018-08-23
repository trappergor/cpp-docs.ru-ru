---
title: '#Ошибка директива (C/C++) | Документация Майкрософт'
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
ms.openlocfilehash: d2da939fe52e41e122ecd4926e34fb9c4be735ae
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541834"
---
# <a name="error-directive-cc"></a>Директива #error (C/C++)
**#Error** директивы выдает сообщение об ошибке, определяемый пользователем во время компиляции, а затем завершает компиляцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>Примечания  
 
Сообщение об ошибке, этой директивой включает *строке токена* параметра. *Строке токена* параметр не подлежит расширению макроса. Эта директива наиболее полезна в ходе предварительной обработки и позволяет уведомлять разработчика о противоречиях в программе или о нарушении ограничений. В следующем примере демонстрируется обработка ошибки во время предварительной обработки.  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>См. также  
 
[Директивы препроцессора](../preprocessor/preprocessor-directives.md)