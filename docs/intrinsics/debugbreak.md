---
title: "__debugbreak | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__debugbreak_cpp"
  - "__debugbreak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "встроенная функция __debugbreak"
  - "точки останова, встроенная функция __debugbreak"
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# __debugbreak
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Блок, относящийся только к системам Microsoft**  
  
 Вызывает точку останова в коде, где пользователю будет предложено запустить отладчик.  
  
## Синтаксис  
  
```  
void __debugbreak();  
```  
  
## Требования  
  
|Встроенная функция|Архитектура|Header|  
|------------------------|-----------------|------------|  
|`__debugbreak`|x86, ARM, [!INCLUDE[vcprx64](../Token/vcprx64_md.md)]|\<intrin.h\>|  
  
## Заметки  
 Встроенная функция компилятора `__debugbreak`, аналогичная функции [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), — это переносимое средство Win32 для создания точки останова.  
  
> [!NOTE]
>  При компиляции с использованием **\/clr** функция, содержащая `__debugbreak`, будет компилироваться в MSIL.  При использовании `asm int 3` функция компилируется в машинный код.  Для получения дополнительной информации см. [\_\_asm](../assembler/inline/asm.md).  
  
 Например:  
  
```  
main() {  
   __debugbreak();  
}  
```  
  
 аналогично  
  
```  
main() {  
   __asm {  
      int 3  
   }  
}  
```  
  
 на компьютере с архитектурой x86.  
  
 Эта процедура доступна только как встроенная функция.  
  
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)