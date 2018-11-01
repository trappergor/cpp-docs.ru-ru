---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: 5c7d5a1cfe16ef3cb1d79617133cd1ceccdfb78c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633519"
---
# <a name="model"></a>.MODEL

Инициализирует модель памяти программы.

## <a name="syntax"></a>Синтаксис

> . МОДЕЛЬ memorymodel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>Параметры

*memorymodel*<br/>
Обязательный параметр, который определяет размер указателей кода и данных.

*langtype*<br/>
Необязательный параметр, который задает соглашение о вызывающих и имен для процедур и открытые символы.

*stackoption*<br/>
Необязательный параметр.

*stackoption* не используется, если *memorymodel* является `FLAT`.

Указание `NEARSTACK` группирует одному физическому сегменту сегмента стека (`DGROUP`) вместе с данными. Регистр стека сегмент (`SS`) предполагается, что для хранения тот же адрес, регистр сегмента данных (`DS`). `FARSTACK` не группируются стек `DGROUP`; таким образом `SS` не равно `DS`.

## <a name="remarks"></a>Примечания

.`MODEL` не используется в [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

В следующей таблице перечислены возможные значения для каждого параметра, ориентируясь на 16-разрядных и 32-разрядных платформах:

|Параметр|32-разрядных значений|16-разрядных значений (поддержка для более ранней разработки 16-разрядных)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|Не используется|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>Код

Примеры, связанные с MASM, загрузить образцы компилятора [примеры Visual C++ и связанную документацию для Visual Studio 2010](http://go.microsoft.com/fwlink/p/?linkid=178749).

В следующем примере показано использование `.MODEL` директива.

## <a name="example"></a>Пример

```asm
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

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>

