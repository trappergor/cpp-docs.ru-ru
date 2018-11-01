---
title: __popcnt16, __popcnt, __popcnt64
ms.date: 11/04/2016
f1_keywords:
- __popcnt64
- __popcnt
- __popcnt16
helpviewer_keywords:
- popcnt instruction
- __popcnt16
- __popcnt64
- __popcnt
ms.assetid: e525b236-adc8-42df-9b9b-8b7d8c245d3b
ms.openlocfilehash: b40d84b919a3418d48b820e5285b523cd602dc92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538173"
---
# <a name="popcnt16-popcnt-popcnt64"></a>__popcnt16, __popcnt, __popcnt64

**Блок, относящийся только к системам Microsoft**

Подсчитывает количество один бит (счетчик заполнения) в 16-, 32- или 64-разрядного целого числа без знака.

## <a name="syntax"></a>Синтаксис

```
unsigned short __popcnt16(
   unsigned short value
);
unsigned int __popcnt(
   unsigned int value
);
unsigned __int64 __popcnt64(
   unsigned __int64 value
);
```

#### <a name="parameters"></a>Параметры

*значение*<br/>
[in] 16-, 32- или 64-разрядное целое число без знака для которого мы хотим счетчик заполнения.

## <a name="return-value"></a>Возвращаемое значение

Номер один бит в `value` параметра.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__popcnt16`|Расширенные побитовой обработки|
|`__popcnt`|Расширенные побитовой обработки|
|`__popcnt64`|Расширенные манипуляция с битами в 64-разрядном режиме.|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Каждый из этих встроенных функций приводит к возникновению ошибки `popcnt` инструкции.  Размер значения, `popcnt` инструкция возвращает совпадает со значением размера аргумента.  В 32-разрядном режиме существует не 64-разрядных регистров общего назначения, поэтому не 64-разрядных `popcnt`.

Чтобы определить аппаратная поддержка для `popcnt` инструкция, вызов `__cpuid` встроенная функция с `InfoType=0x00000001` и проверьте часть 23 `CPUInfo[2] (ECX)`. Этот бит равен 1, если инструкция поддерживается и 0 в противном случае. Если вы запустите код, использующий этой встроенной функции на оборудовании, которое не поддерживает `popcnt` инструкции, результаты будут непредсказуемыми.

## <a name="example"></a>Пример

```
#include <iostream>
#include <intrin.h>
using namespace std;

int main()
{
  unsigned short us[3] = {0, 0xFF, 0xFFFF};
  unsigned short usr;
  unsigned int   ui[4] = {0, 0xFF, 0xFFFF, 0xFFFFFFFF};
  unsigned int   uir;

  for (int i=0; i<3; i++) {
    usr = __popcnt16(us[i]);
    cout << "__popcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __popcnt(ui[i]);
    cout << "__popcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}

```

```Output
__popcnt16(0x0) = 0
__popcnt16(0xff) = 8
__popcnt16(0xffff) = 16
__popcnt(0x0) = 0
__popcnt(0xff) = 8
__popcnt(0xffff) = 16
__popcnt(0xffffffff) = 32
```

**Завершение блока, относящегося только к системам Майкрософт**

Авторское право 2007 Дополнительно Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)
