---
title: Предварительно определенные правила
ms.date: 11/04/2016
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
ms.openlocfilehash: e3b30957c15d6fb4eabb72381bad43a2d622a25d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413203"
---
# <a name="predefined-rules"></a>Предварительно определенные правила

Предварительно определенных правилах определения использовать макросы команду и параметры, предоставленные NMAKE.

|Правило|Команда|Значение по умолчанию<br /><br /> action|Batch<br /><br /> Правило|Платформа nmake работает на|
|----------|-------------|------------------------|--------------------|----------------------------|
|.asm.exe|$(AS) $(AFLAGS) $&LT;|ML $<|Нет|x86|
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML /c $<|да|x86|
|.asm.exe|$(AS) $(AFLAGS) $&LT;|ML64 $<|Нет|X64|
|. asm.obj|$(AS) $(AFLAGS) /c $<|ML64 /c $<|да|X64|
|.c.exe|$(CC) $(CFLAGS) $&LT;|CL $<|Нет|все|
|. c.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|
|.cc.exe|$(CC) $(CFLAGS) $&LT;|CL $<|Нет|все|
|. cc.obj|$(CC) $(CFLAGS) /c $<|CL /c $<|да|все|
|. cpp.exe|$(CPP) $(CPPFLAGS) $&LT;|CL $<|Нет|все|
|.cpp.obj|$(CPP) $(CPPFLAGS) /c $<|CL /c $<|да|все|
|.cxx.exe|$(CXX) $(CXXFLAGS) $&LT;|CL $<|Нет|все|
|.cxx.obj|$(CXX) $(CXXFLAGS) /c $<|CL /c $<|да|все|
|. rc.res|$(RC) $(RFLAGS) /r $<|Версия-кандидат /r $<|Нет|все|

## <a name="see-also"></a>См. также

[Правила вывода](../build/inference-rules.md)
