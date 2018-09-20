---
title: __vmx_vmptrld | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmptrld
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmptrld intrinsic
- VMPTRLD instruction
ms.assetid: 95c9ec5b-1a81-41ba-983e-327bd6a65fcb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a7126dc3b6a0ece4a5b7627859d0b80abf962d88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46429108"
---
# <a name="vmxvmptrld"></a>__vmx_vmptrld

**Блок, относящийся только к системам Microsoft**

Загружает указатель на текущую структуру управления виртуальной машины (VMCS) из указанного адреса.

## <a name="syntax"></a>Синтаксис

```
int __vmx_vmptrld( 
   unsigned __int64 *VmcsPhysicalAddress 
);
```

#### <a name="parameters"></a>Параметры

[in] *`VmcsPhysicalAddress` адрес, где хранится указатель VMCS.

## <a name="return-value"></a>Возвращаемое значение

0, операция выполнена успешно.

1 операция завершилась с расширенные сведения о состоянии в `VM-instruction error field` текущей структуре vmcs.

2 сбой операции без сведений о состоянии.

## <a name="remarks"></a>Примечания

Указатель VMCS — это 64-разрядный физический адрес.

`__vmx_vmptrld` Функция эквивалентна `VMPTRLD` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/en-us/articles/intel-sdm) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmptrld`|X64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmptrst](../intrinsics/vmx-vmptrst.md)