---
title: .MODEL
ms.date: 08/30/2018
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: c409bf10a2f863c380cda6b4822583ffb3787da6
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934099"
---
# <a name="model"></a>.MODEL

Инициализирует модель памяти программы.

## <a name="syntax"></a>Синтаксис

> .MODEL memorymodel [[, langtype]] [[, stackoption]]

### <a name="parameters"></a>Параметры

*memorymodel*<br/>
Обязательный параметр, который определяет размер кода и указателей данных.

*langtype*<br/>
Необязательный параметр, который задает соглашения о вызовах и именовании для процедур и открытых символов.

*stackoption*<br/>
Необязательный параметр.

*stackoption* не используется, если *memorymodel* имеет значение `FLAT`.

Указание `NEARSTACK` группирует сегмент стека в один физический сегмент (`DGROUP`) наряду с данными. Предполагается, что в регистре сегмента стека (`SS`) хранится тот же адрес, что и в регистре сегмента данных (`DS`). `FARSTACK` не группирует стек с `DGROUP`; таким образом `SS` не равно `DS`.

## <a name="remarks"></a>Примечания

.`MODEL` не используется в [MASM для x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

В следующей таблице перечислены возможные значения для каждого параметра при нацеливании на 16-разрядные и 32-разрядные платформы:

|Параметр|32-разрядные значения|16-разрядные значения (поддержка более ранней разработки 16-разрядных приложений)|
|---------------|--------------------|----------------------------------------------------------------|
|*memorymodel*|`FLAT`|`TINY`, `SMALL`, `COMPACT`, `MEDIUM`, `LARGE`, `HUGE`, `FLAT`|
|*langtype*|`C`, `STDCALL`|`C`, `BASIC`, `FORTRAN`, `PASCAL`, `SYSCALL`, `STDCALL`|
|*stackoption*|Не используется|`NEARSTACK`, `FARSTACK`|

## <a name="code"></a>Код

Для получения примеров, связанных с MASM, скачайте примеры компилятора на странице [примеров кода на Visual C++ и связанной документации для Visual Studio 2010](https://go.microsoft.com/fwlink/p/?linkid=178749).

В следующем примере иллюстрируется использование директивы `.MODEL`.

## <a name="example"></a>Пример

```asm
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

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
