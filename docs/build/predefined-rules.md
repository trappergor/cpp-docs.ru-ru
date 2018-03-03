---
title: "Предопределенные правила | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3be1c8eea7b11f60e9ce9a7cbf5ebc0c2b99b698
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="predefined-rules"></a>Предварительно определенные правила
Предварительно определенных правилах определения использовать предоставленные NMAKE макросы команд и параметров.  
  
|Правило|Команда|По умолчанию<br /><br /> action|Batch<br /><br /> Правило|Платформа nmake работает на|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|. asm.exe|$(AS) $(AFLAGS) $<|ML $<|Нет|x86|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML /c $<|да|x86|  
|. asm.exe|$(AS) $(AFLAGS) $<|ML64 $<|Нет|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|/c ML64 $<|да|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. c.exe|$(CC) $(CFLAGS) $<|CL $<|нет|все|  
|. c.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|  
|. cc.exe|$(CC) $(CFLAGS) $<|CL $<|нет|все|  
|. cc.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|  
|. cpp.exe|$(CPP) $(CPPFLAGS) $<|CL $<|нет|все|  
|. cpp.obj|$(CPP) $(CPPFLAGS) /c $<|CL /c $<|да|все|  
|. cxx.exe|$(CXX) $(CXXFLAGS) $<|CL $<|нет|все|  
|. cxx.obj|$(CXX) $(CXXFLAGS) /c $<|CL /c $<|да|все|  
|. rc.res|$(RC) $(RFLAGS) /r $<|Версия-кандидат /r $<|Нет|все|  
  
## <a name="see-also"></a>См. также  
 [Правила вывода](../build/inference-rules.md)