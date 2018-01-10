---
title: "Хранение битовых полей | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4816a241-1580-4d1c-82ed-13d359733959
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1be04ba4c68b2629a5e765788af95a203ae06b34
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="storage-of-bit-fields"></a>Хранение битовых полей
**ANSI 3.5.2.1** Порядок назначения битовых полей в целом числе  
  
 Битовые поля в целом числе назначаются в направлении от младшего разряда к старшему. В приведенном ниже коде  
  
```  
struct mybitfields  
{  
   unsigned a : 4;  
   unsigned b : 5;  
   unsigned c : 7;  
} test;  
  
int main( void )  
{  
   test.a = 2;  
   test.b = 31;  
   test.c = 0;  
}  
```  
  
 биты размещаются следующим образом:  
  
```  
00000001 11110010  
cccccccb bbbbaaaa  
```  
  
 Поскольку в процессорах 80x86 младший байт целочисленных значений размещается перед старшим байтом, указанное выше целое число 0x01F2 будет храниться в физической памяти в следующем виде: 0xF2 0x01.  
  
## <a name="see-also"></a>См. также  
 [Структуры, объединения, перечисления и битовые поля](../c-language/structures-unions-enumerations-and-bit-fields.md)