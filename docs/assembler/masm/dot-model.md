---
title: ".MODEL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".MODEL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".MODEL directive"
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .MODEL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Инициализирует модель памяти программы.  
  
## Синтаксис  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### Параметры  
 `memorymodel`  
 Обязательный параметр, который определяет размер указателей кода и данных.  
  
 `langtype`  
 Необязательный параметр, который задает соглашения именования и вызова процедур и открытые символы.  
  
 `stackoption`  
 Необязательный параметр.  
  
 `stackoption`is not used if `memorymodel` is `FLAT`.  
  
 Указание `NEARSTACK` группирует сегмент стека в один физический сегмент \(`DGROUP`\) вместе с данными.  Регистр сегмента стека \(`SS`\) предполагается, что содержат один и тот же адрес как сегментным регистром данных \(`DS`\).  `FARSTACK`Не группировать стека с `DGROUP`; Таким образом `SS` не равен `DS`.  
  
## Заметки  
 .`MODEL`не используется в [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 В следующей таблице перечислены возможные значения для каждого параметра, когда выбор 16\-разрядные и 32\-разрядных платформ:  
  
|Параметр|32\-разрядные значения|16\-битовых значений \(поддержка разработки предыдущих 16 бит\)|  
|--------------|----------------------------|---------------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|Не используется|`NEARSTACK`, `FARSTACK`|  
  
## Код  
 Образцы, связанные с MASM, загрузите образцы компилятора от [Примеры Visual C\+\+ и сопутствующую документацию для 2010 Visual Studio](см.?LinkID%20=%20178749).  
  
 В следующем примере показано использование `.MODEL` директивы.  
  
## Пример  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
ifndef X64  
.686p  
.XMM  
.model flat, C  
endif  
  
.data  
; user data  
  
.code  
; user code  
  
fxn PROC public  
  xor eax, eax ; zero function return value  
  ret  
fxn ENDP  
  
end  
```  
  
## См. также  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [Примеры Visual C\+\+ и сопутствующую документацию для 2010 Visual Studio](см.?LinkID%20=%20178749)