---
title: Предварительно определенные правила
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: 7a922a239306f10121791caa8f9f088cea88c019
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827333"
---
# <a name="predefined-rules"></a>Предварительно определенные правила

Предварительно определенных правилах определения использовать макросы команду и параметры, предоставленные NMAKE.

|Правило|Команда|Значение по умолчанию<br /><br /> action|Batch<br /><br /> Правило|Платформа nmake работает на|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$(AS) $(AFLAGS) $&LT;|ML $<|нет|x86|
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML /c $<|да|x86|
|.asm.exe|$(AS) $(AFLAGS) $&LT;|ML64 $<|нет|x64|
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML64 /c $<|да|x64|
|.c.exe|$(CC) $(CFLAGS) $&LT;|CL $<|нет|все|
|. c.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|
|.cc.exe|$(CC) $(CFLAGS) $&LT;|CL $<|нет|все|
|. cc.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|
|. cpp.exe|$(CPP) $(CPPFLAGS) $&LT;|CL $<|нет|все|
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|CL /c $<|да|все|
|.cxx.exe|$(CXX) $(CXXFLAGS) $&LT;|CL $<|нет|все|
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|CL /c $<|да|все|
|. rc.res|$(RC) $(RFLAGS) /r $<|Версия-кандидат /r $<|нет|все|

## <a name="see-also"></a>См. также

[Правила вывода](inference-rules.md)
