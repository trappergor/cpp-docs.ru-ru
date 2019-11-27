---
title: .MODEL
ms.date: 11/05/2019
f1_keywords:
- .MODEL
helpviewer_keywords:
- .MODEL directive
ms.assetid: 057f00df-1515-4c55-852a-d936c8a34b53
ms.openlocfilehash: bfc114a6e71c0eb0ae70005c2657871b6c9e9692
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74398115"
---
# <a name="model-32-bit-masm"></a>. МОДЕЛЬ (32-разрядный MASM)

Инициализирует модель памяти программы. (только 32-разрядный MASM.)

## <a name="syntax"></a>Синтаксис

> **. Память модели** *— модель* ⟦ __,__ *язык — тип*⟧ ⟦ __,__ *Stack-Option*⟧

### <a name="parameters"></a>Параметры

*память —\ модели*
Обязательный параметр, который определяет размер кода и указателей данных.

*тип\ языка*
Необязательный параметр, который задает соглашения о вызовах и именовании для процедур и открытых символов.

\ *параметров стека*
Необязательный параметр.

*параметр Stack-* не используется, если *модель памяти* **плоская**.

Указание **неарстакк** группирует сегмент стека в один физический сегмент (**дграуп**) вместе с данными. Предполагается, что регистр сегмента стека (**SS**) содержит тот же адрес, что и регистр сегмента данных (**DS**). **Фарстакк** не будет группировать стек с **дграуп**; таким, **SS** не равно **DS**.

## <a name="remarks"></a>Примечания

**. МОДЕЛЬ** не используется в [MASM для x64 (ml64. exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).

В следующей таблице перечислены возможные значения для каждого параметра при нацеливании на 16-разрядные и 32-разрядные платформы:

|Параметр|32-разрядные значения|16-разрядные значения (поддержка более ранней разработки 16-разрядных приложений)|
|---------------|--------------------|----------------------------------------------------------------|
|*память-модель*|**ВЫПУКЛАЯ**|**мелкий, Малый**, **компактный**, **средний**, **крупный**, **огромный**, **плоский**|
|*Тип языка*|**C**, **STDCALL**|**C**, **Basic**, **Fortran**, **Pascal**, **syscall**, **STDCALL**|
|*Stack-параметр*|Не используется|**неарстакк**, **фарстакк**|

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

## <a name="see-also"></a>См. также:

[Справочник по директивам](../../assembler/masm/directives-reference.md)
