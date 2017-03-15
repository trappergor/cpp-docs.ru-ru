---
title: "Предварительно определенные правила | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "правила, предварительно определенные"
  - "Программа NMAKE, предварительно определенные правила"
  - "предварительно определенные правила (NMAKE)"
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Предварительно определенные правила
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В предварительно определенных правилах определения используются команды, предоставленные NMAKE и макросы параметров.  
  
|Правило|Команда|По умолчанию<br /><br /> действие|Batch<br /><br /> Правило|Платформа nmake работает на|  
|-------------|-------------|-------------------------------|-----------------------|---------------------------------|  
|.asm.exe|$ \(AS\) $ \(AFLAGS\) $\<|ml $\<|нет|x86|  
|.asm.obj|$ \(AS\) $ \(AFLAGS\) \/c $\<|ml \/c $\<|да|x86|  
|.asm.exe|$ \(AS\) $ \(AFLAGS\) $\<|ml64 $\<|нет|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|.asm.obj|$ \(AS\) $ \(AFLAGS\) \/c $\<|ml64 \/c $\<|да|[!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|  
|.c.exe|$ \(CC\) $ \(CFLAGS\) $\<|cl $\<|нет|все|  
|.c.obj|$ \(CC\) $ \(CFLAGS\) \/c $\<|cl \/c $\<|да|все|  
|.cc.exe|$ \(CC\) $ \(CFLAGS\) $\<|cl $\<|нет|все|  
|.cc.obj|$ \(CC\) $ \(CFLAGS\) \/c $\<|cl \/c $\<|да|все|  
|.cpp.exe|$ \(CPP\) $ \(CPPFLAGS\) $\<|cl $\<|нет|все|  
|.cpp.obj|$ \(CPP\) $ \(CPPFLAGS\) \/c $\<|cl \/c $\<|да|все|  
|.cxx.exe|$ \(CXX\) $ \(CXXFLAGS\) $\<|cl $\<|нет|все|  
|.cxx.obj|$ \(CXX\) $ \(CXXFLAGS\) \/c $\<|cl \/c $\<|да|все|  
|.rc.res|$ \(RC\) $ \(RFLAGS\) \/r $\<|rc \/r $\<|нет|все|  
  
## См. также  
 [Правила вывода](../build/inference-rules.md)