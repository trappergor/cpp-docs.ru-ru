---
title: __lzcnt16, __lzcnt, __lzcnt64
ms.date: 11/04/2016
f1_keywords:
- __lzcnt64
- __lzcnt16
- __lzcnt
helpviewer_keywords:
- __lzcnt intrinsic
- lzcnt instruction
- lzcnt16 intrinsic
- lzcnt intrinsic
- __lzcnt16 intrinsic
- lzcnt64 intrinsic
- __lzcnt64 intrinsic
ms.assetid: 412113e7-052e-46e5-8bfa-d5ad72abc10e
ms.openlocfilehash: 333d9f2b23fb90388af8395945256956c9222ab9
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041342"
---
# <a name="lzcnt16-lzcnt-lzcnt64"></a>__lzcnt16, __lzcnt, __lzcnt64

**Блок, относящийся только к системам Microsoft**

Счетчики количество начальные нули в 16-, 32- или 64-разрядное целое число.

## <a name="syntax"></a>Синтаксис

```
unsigned short __lzcnt16(
   unsigned short value
);
unsigned int __lzcnt(
   unsigned int value
);
unsigned __int64 __lzcnt64(
   unsigned __int64 value
);
```

#### <a name="parameters"></a>Параметры

*value*<br/>
[in] 16-, 32- или 64-разрядное целое число без знака для проверки на наличие начальных нулей.

## <a name="return-value"></a>Возвращаемое значение

Число начальных нулей в `value` параметра. Если `value` равно нулю, возвращаемое значение — это размер входной операнд (16, 32 или 64). Если самый старший бит `value` равна 1, возвращаемое значение равно нулю.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__lzcnt16`|AMD: Расширенные побитовой обработки (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt`|AMD: Расширенные побитовой обработки (ABM)<br /><br /> Intel: Haswell|
|`__lzcnt64`|AMD: Расширенные бит манипуляции (ABM) в 64-разрядном режиме.<br /><br /> Intel: Haswell|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Каждый из этих встроенных функций приводит к возникновению ошибки `lzcnt` инструкции.  Размер значения, `lzcnt` инструкция возвращает совпадает со значением размера аргумента.  В 32-разрядном режиме существует не 64-разрядных регистров общего назначения, поэтому не 64-разрядных `lzcnt`.

Чтобы определить аппаратная поддержка для `lzcnt` вызов инструкции `__cpuid` встроенная функция с `InfoType=0x80000001` и проверьте бит 5 `CPUInfo[2] (ECX)`. Этот бит будет 1, если инструкция поддерживается и 0 в противном случае. Если вы запустите код, использующий этой встроенной функции на оборудовании, которое не поддерживает `lzcnt` инструкции, результаты будут непредсказуемыми.

Для процессоров Intel, которые не поддерживают `lzcnt` кодировку байтов инструкции выполнения инструкции, как `bsr` (бит обратного просмотра). Если переносимость кода представляет собой проблему, можно использовать `_BitScanReverse` внутренние вместо этого. Дополнительные сведения см. в разделе [_BitScanReverse _BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md).

## <a name="example"></a>Пример

```
// Compile this test with: /EHsc
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
    usr = __lzcnt16(us[i]);
    cout << "__lzcnt16(0x" << hex << us[i] << ") = " << dec << usr << endl;
  }

  for (int i=0; i<4; i++) {
    uir = __lzcnt(ui[i]);
    cout << "__lzcnt(0x" << hex << ui[i] << ") = " << dec << uir << endl;
  }
}
```

```Output
__lzcnt16(0x0) = 16
__lzcnt16(0xff) = 8
__lzcnt16(0xffff) = 0
__lzcnt(0x0) = 32
__lzcnt(0xff) = 24
__lzcnt(0xffff) = 16
__lzcnt(0xffffffff) = 0
```

**Завершение блока, относящегося только к системам Майкрософт**

Некоторые части этого содержимого, авторские права, 2007 Advanced Micro устройств, Inc. Все права защищены. Воспроизвести с помощью разрешения Advanced Micro устройств, Inc.

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)
