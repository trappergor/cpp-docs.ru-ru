---
title: __vmx_vmptrst
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmptrst
helpviewer_keywords:
- __vmx_vmptrst intrinsic
- VMPTRST instruction
ms.assetid: 8dc66e47-03a0-41b0-8e25-c1485f42817a
ms.openlocfilehash: 5ef02dd4401e0c10a84be008d7cb25841e0359cd
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029519"
---
# <a name="vmxvmptrst"></a>__vmx_vmptrst

**Блок, относящийся только к системам Microsoft**

Хранит указатель на текущий структуру управления виртуальной машины (VMCS) по указанному адресу.

## <a name="syntax"></a>Синтаксис

```
void __vmx_vmptrst(
   unsigned __int64 *VmcsPhysicalAddress
);
```

### <a name="parameters"></a>Параметры

*VmcsPhysicalAddress*<br/>
[in] Адрес, где хранится указатель текущей VMCS.

## <a name="remarks"></a>Примечания

Указатель VMCS — это 64-разрядный физический адрес.

Функция `__vmx_vmptrst` эквивалентна инструкции компьютера `VMPTRST` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmptrst`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrld](../intrinsics/vmx-vmptrld.md)