---
title: "Эффекты буферизации | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- buffers, effects of buffering
- buffering, effects of
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4073397867eeec176b02ccd67eeb1ac9cdd0ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="effects-of-buffering"></a>Эффекты буферизации
В следующем примере демонстрируются эффекты буферизации. Вы могли ожидать, что программа выведет `please wait`, подождет 5 секунд и затем продолжит выполнение. Однако такое поведение необязательно, так как выходные данные помещаются в буфер.  
  
```  
// effects_buffering.cpp  
// compile with: /EHsc  
#include <iostream>  
#include <time.h>  
using namespace std;  
  
int main( )  
{  
   time_t tm = time( NULL ) + 5;  
   cout << "Please wait...";  
   while ( time( NULL ) < tm )  
      ;  
   cout << "\nAll done" << endl;  
}  
```  
  
 Чтобы программа работала логично, объект `cout` должен опустошать себя перед выводом сообщения. Чтобы сохранить объект `ostream` , отправьте ему манипулятор `flush` :  
  
```  
cout <<"Please wait..." <<flush;  
```  
  
 Это действие сохраняет буфер, гарантируя вывод сообщения до ожидания. Можно также использовать `endl` манипулятор, который сохраняет буфер и выводит возврата каретки, или можно использовать `cin` объекта. Этот объект (с объектами `cerr` или `clog` ) обычно привязывается к объекту `cout` . Таким образом, любое использование `cin` (или объектов `cerr` или `clog` ) сохраняет объект `cout` .  
  
## <a name="see-also"></a>См. также  
 [Потоки вывода](../standard-library/output-streams.md)

