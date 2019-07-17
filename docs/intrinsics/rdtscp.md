---
title: __rdtscp
ms.date: 07/11/2019
f1_keywords:
- __rdtscp
helpviewer_keywords:
- rdtscp intrinsic
- __rdtscp intrinsic
- rdtscp instruction
ms.assetid: f17d9a9c-88bb-44e0-b69d-d516bc1c93ee
ms.openlocfilehash: b8a31c6d19cd171cbe909c75a27c2389866bd578
ms.sourcegitcommit: 0e3da5cea44437c132b5c2ea522bd229ea000a10
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/12/2019
ms.locfileid: "67861117"
---
# <a name="rdtscp"></a>__rdtscp

**Блок, относящийся только к системам Microsoft**

Создает `rdtscp` записывает инструкции, `TSC_AUX[31:0`] в памяти и возвращает счетчик отметок времени 64-разрядных (`TSC)` результат.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __rdtscp(
   unsigned int * Aux
);
```

#### <a name="parameters"></a>Параметры

*AUX*<br/>
[out] Указатель на расположение, которое будет содержать содержимое регистра конкретного компьютера `TSC_AUX[31:0]`.

## <a name="return-value"></a>Возвращаемое значение

Счетчик тактов 64-разрядного целого числа без знака.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__rdtscp`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция создает `rdtscp` инструкции. Чтобы определить аппаратная поддержка для данной инструкции, вызовите `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 27 `CPUInfo[3] (EDX)`. Этот бит равен 1, если инструкция поддерживается и 0 в противном случае.  Если вы запустите код, использующий этой встроенной функции на оборудовании, которое не поддерживает `rdtscp` инструкции, результаты будут непредсказуемыми.

Эта инструкция ожидает, пока не выполнены все предыдущие инструкции и всех предыдущих загрузок видимы глобально. Тем не менее это не инструкцию сериализации. См. в разделе руководства Intel и AMD, Дополнительные сведения.

Смысл значения в `TSC_AUX[31:0]` зависит от операционной системы.

## <a name="example"></a>Пример

```cpp
#include <intrin.h>
#include <stdio.h>
int main()
{
    unsigned __int64 i;
    unsigned int ui;
    i = __rdtscp(&ui);
    printf_s("%I64d ticks\n", i);
    printf_s("TSC_AUX was %x\n", ui);
}
```

```Output
3363423610155519 ticks
TSC_AUX was 0
```

**Завершение блока, относящегося только к системам Майкрософт**


## <a name="see-also"></a>См. также

[__rdtsc](../intrinsics/rdtsc.md)<br/>
[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)