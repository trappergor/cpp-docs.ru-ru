---
title: Предопределенные правила | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0a21847bb9363099fa64825b45a90003de053da
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369764"
---
# <a name="predefined-rules"></a>Предварительно определенные правила
Предварительно определенных правилах определения использовать предоставленные NMAKE макросы команд и параметров.  
  
|Правило|Команда|Значение по умолчанию<br /><br /> action|Batch<br /><br /> Правило|Платформа nmake работает на|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|. asm.exe|$(AS) $(AFLAGS) $&LT;|ML $<|Нет|x86|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML /c $<|да|x86|  
|. asm.exe|$(AS) $(AFLAGS) $&LT;|ML64 $<|Нет|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|/c ML64 $<|да|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. c.exe|$(CC) $(CFLAGS) $&LT;|CL $<|нет|все|  
|. c.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|  
|. cc.exe|$(CC) $(CFLAGS) $&LT;|CL $<|нет|все|  
|. cc.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|  
|. cpp.exe|$(CPP) $(CPPFLAGS) $&LT;|CL $<|нет|все|  
|. cpp.obj|$(CPP) $(CPPFLAGS) /c $<|CL /c $<|да|все|  
|. cxx.exe|$(CXX) $(CXXFLAGS) $&LT;|CL $<|нет|все|  
|. cxx.obj|$(CXX) $(CXXFLAGS) /c $<|CL /c $<|да|все|  
|. rc.res|$(RC) $(RFLAGS) /r $<|Версия-кандидат /r $<|Нет|все|  
  
## <a name="see-also"></a>См. также  
 [Правила вывода](../build/inference-rules.md)