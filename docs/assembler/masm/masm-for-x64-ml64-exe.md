---
title: "MASM for x64 (ml64.exe) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ml64.exe"
  - "ml"
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# MASM for x64 (ml64.exe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ml64.exe ассемблер, который принимает [!INCLUDE[vcprx64](../Token/vcprx64_md.md)] язык ассемблера.  Дополнительные сведения о параметрах компилятора ml64.exe см. в разделе [ML and ML64 Command\-Line Reference](../../assembler/masm/ml-and-ml64-command-line-reference.md).  
  
 Встроенное asm не поддерживается [!INCLUDE[vcprx64](../Token/vcprx64_md.md)].  Используйте MASM \(или внутренних функций компилятора[x64 Intrinsics](http://msdn.microsoft.com/ru-ru/5d1f5d3e-156e-4ebf-932e-fd09be7ced62)\).  
  
 2 Временного решения отдельную сборку с MASM \(64\-разрядная версия\) и полностью поддерживает внутренние функции компилятора.  Мы добавили множество встроенных функций для того, чтобы позволить клиентам использовать инструкции \(например специальн\-функции.  просмотр привилигированного, бита\/предоставленный тест,…\) и т д как закрыть кроссплатформенный образа.  
  
## рекомендации ml64\-Specific  
 Используйте следующие рекомендации с ml64.exe:  
  
-   [.ALLOCSTACK](../Topic/.ALLOCSTACK.md)  
  
-   [.ENDPROLOG](../Topic/.ENDPROLOG.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../Topic/.PUSHREG.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
 Кроме того, [PROC](../../assembler/masm/proc.md) директива была обновлена для использования с ml64.exe.  
  
## 32 \- режим адреса \(переопределение размера адреса\)  
 MASM испустит переопределение размера адреса 0x67, если операнд памяти включает 32 регистров.  Например, в следующих примерах вызывают переопределение размера адреса быть испущенным:  
  
```  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
 MASM предполагается, что если смещение отображается не связано с пакетом обновления 32 \(sp2\) в качестве операнда 64 \(sp2\) адресации памяти.  В настоящее время не поддерживаются пакетом обновления 32 \(sp2\) решить с теми операндами.  
  
 Наконец, смешивание размеры регистра внутри операнда памяти, как показано в следующем коде, off, вызовут ошибку.  
  
```  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## См. также  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)