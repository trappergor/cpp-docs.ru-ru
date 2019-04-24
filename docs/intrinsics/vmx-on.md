---
title: __vmx_on
ms.date: 11/04/2016
f1_keywords:
- __vmx_on
helpviewer_keywords:
- VMXON instruction
- __vmx_on intrinsic
ms.assetid: 16804991-6a75-4adf-8ec2-bc95acfa4801
ms.openlocfilehash: de903eeeb29e3c194a36ccb4cb038ba89b8ea82f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028108"
---
# <a name="vmxon"></a>__vmx_on

**Блок, относящийся только к системам Microsoft**

Активирует операции расширения (VMX) виртуальной машины в процессоре.

## <a name="syntax"></a>Синтаксис

```
unsigned char __vmx_on(
   unsigned __int64 *VmsSupportPhysicalAddress
);
```

#### <a name="parameters"></a>Параметры

*VmsSupportPhysicalAddress*<br/>
[in] Указатель на 64-разрядный физический адрес, который указывает на структуру управления виртуальной машины (VMCS).

## <a name="return-value"></a>Возвращаемое значение

|Значение|Смысл|
|-----------|-------------|
|0|Операция успешно выполнена.|
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|
|2|Сбой операции без сведений о состоянии.|

## <a name="remarks"></a>Примечания

`__vmx_on` Соответствует функции `VMXON` инструкции компьютера. Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_on`|X64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)