---
title: сообщение | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- message_CPP
- vc-pragma.message
dev_langs:
- C++
helpviewer_keywords:
- message pragma
- pragmas, message
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3ce9091fe380f7d255dd321dbb9eb5ca7134b8d
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/10/2018
ms.locfileid: "42541284"
---
# <a name="message"></a>сообщение
Отправляет строковый литерал в стандартный вывод, не завершая компиляцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#pragma message( messagestring )  
```  
  
## <a name="remarks"></a>Примечания  

Типичное применение **сообщение** pragma — Отображать информационные сообщения во время компиляции.  
  
*Messagestring* параметр может быть макросом, который развертывается в строковый литерал, и можно сцепить эти макросы со строковыми литералами в любой комбинации.  
  
При использовании предопределенного макроса в **сообщение** pragma, макрос должен вернуть строку, в противном случае вам придется преобразовать вывод макроса в строку.  
  
В следующем фрагменте кода используется **сообщение** директивы pragma, для отображения сообщений во время компиляции:  
  
```cpp  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## <a name="see-also"></a>См. также  
 
[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)