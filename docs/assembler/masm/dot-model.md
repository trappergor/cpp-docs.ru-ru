---
title: . МОДЕЛЬ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .MODEL
dev_langs:
- C++
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2814b1b6cc4483807f77989ff4fbb70929400d6e
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057751"
---
# <a name="model"></a>.MODEL
Инициализирует модель памяти программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
.MODEL memorymodel [[, langtype]] [[, stackoption]]  
```  
  
#### <a name="parameters"></a>Параметры  
 `memorymodel`  
 Обязательный параметр, который определяет размер указателей кода и данных.  
  
 `langtype`  
 Необязательный параметр, который задает соглашение о вызовах и именования для процедур и открытые символы.  
  
 `stackoption`  
 Необязательный параметр.  
  
 `stackoption` не используется, если `memorymodel` — `FLAT`.  
  
 Указание `NEARSTACK` группирует сегмент стека по одному физическому сегменту (`DGROUP`) вместе с данными. Регистр стека сегмента (`SS`) предполагается, что для хранения тот же адрес, регистр сегмента данных (`DS`). `FARSTACK` не группируются стек с `DGROUP`; таким образом `SS` не равно `DS`.  
  
## <a name="remarks"></a>Примечания  
 .`MODEL` не используется в [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
 В следующей таблице перечислены возможные значения для каждого параметра, ориентируясь на 16-разрядных и 32-разрядных платформах:  
  
|Параметр|32-разрядные значения|16-разрядных значений (поддержка более ранних разработки 16-разрядные)|  
|---------------|--------------------|----------------------------------------------------------------|  
|`memorymodel`|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|  
|`langtype`|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|  
|`stackoption`|Не используется|`NEARSTACK`, `FARSTACK`|  
  
## <a name="code"></a>Код  
 Образцы, связанные с MASM, загрузите образцы компилятора [примеры Visual C++ и сопутствующую документацию для Visual Studio 2010](http://go.microsoft.com/fwlink/p/?linkid=178749).  
  
 В следующем примере показано использование `.MODEL` директивы.  
  
## <a name="example"></a>Пример  
  
```  
; file simple.asm  
; For x86 (32-bit), assemble with debug information:   
;   ml -c -Zi simple.asm  
; For x64 (64-bit), assemble with debug information:   
;   ml64 -c -DX64 -Zi simple.asm  
;  
; In this sample, the 'X64' define excludes source not used   
;  when targeting the x64 architecture  
  
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
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)   
 [Примеры Visual C++ и сопутствующую документацию для Visual Studio 2010](http://go.microsoft.com/fwlink/p/?linkid=178749)