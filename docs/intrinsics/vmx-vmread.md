---
title: __vmx_vmread
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmread
helpviewer_keywords:
- VMREAD instruction
- __vmx_vmread intrinsic
ms.assetid: 08bdd7a0-6435-4ea6-b9a0-f592d870e5aa
ms.openlocfilehash: 0a4528bed4426ce5b611e986a69f4b0b8c750548
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499103"
---
# <a name="vmxvmread"></a>__vmx_vmread

**Блок, относящийся только к системам Microsoft**

Считывает указанное поле из текущую структуру управления виртуальной машины (VMCS) и помещает его в указанном расположении.

## <a name="syntax"></a>Синтаксис

```
unsigned char __vmx_vmread(
   size_t Field,
   size_t *FieldValue
);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*Поле*|[in] Поле VMCS для чтения.|
|*FieldValue*|[in] Указатель на расположение для хранения значения чтения из VMCS поле, указанное параметром `Field` параметр.|

## <a name="return-value"></a>Возвращаемое значение

|Значение|Смысл|
|-----------|-------------|
|0|Операция успешно выполнена.|
|1|Не удалось выполнить операцию; расширенные сведения о состоянии доступны в `VM-instruction error field` текущей структуре VMCS.|
|2|Сбой операции без сведений о состоянии.|

## <a name="remarks"></a>Примечания

Функция `__vmx_vmread` эквивалентна инструкции компьютера `VMREAD` . Значение `Field` параметр является индекс кодировке поля, который описан в документации Intel. Дополнительные сведения в документе «Intel Virtualization технические спецификации для архитектуры IA-32 Intel,» номер документа C97063-002, на [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта, а затем см. в приложении С этим документом .

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__vmx_vmread`|X64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmwrite](../intrinsics/vmx-vmwrite.md)