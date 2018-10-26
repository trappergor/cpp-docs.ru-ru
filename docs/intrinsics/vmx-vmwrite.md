---
title: __vmx_vmwrite | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __vmx_vmwrite
dev_langs:
- C++
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f333a37972a31b5815a05797bfabb603f5a26947
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/05/2018
ms.locfileid: "48820689"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite

**Блок, относящийся только к системам Microsoft**

Записывает заданное значение указанного поля в текущей структуре управления виртуальной машины (VMCS).

## <a name="syntax"></a>Синтаксис

```
unsigned char __vmx_vmwrite( 
   size_t Field,
   size_t FieldValue
);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание:|
|---------------|-----------------|
|*Поле*|[in] Поле VMCS для записи.|
|*FieldValue*|[in] Значение для записи в поле VMCS.|

## <a name="return-value"></a>Возвращаемое значение

0, операция выполнена успешно.

1 операция завершилась с расширенные сведения о состоянии в `VM-instruction error field` текущей структуре vmcs.

2 сбой операции без сведений о состоянии.

## <a name="remarks"></a>Примечания

`__vmx_vmwrite` Функция эквивалентна `VMWRITE` инструкции компьютера. Значение `Field` параметр является индекс кодировке поля, который описан в документации Intel. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/articles/intel-sdm) к сайту, а затем изучите приложения C, документ.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmwrite`|X64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)