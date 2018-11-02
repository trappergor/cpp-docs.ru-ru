---
title: __svm_vmrun
ms.date: 11/04/2016
f1_keywords:
- __svm_vmrun
helpviewer_keywords:
- __svm_vmrun intrinsic
- VMRUN instruction
ms.assetid: ae98a781-fc17-47b2-b40f-86fcebf1867b
ms.openlocfilehash: ffedf366453a800ce420914376b8d9bb441a602a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603567"
---
# <a name="svmvmrun"></a>__svm_vmrun

**Блок, относящийся только к системам Microsoft**

Запускает выполнение кода гостевой виртуальной машины, соответствующий блок управления указанной виртуальной машины (VMCB).

## <a name="syntax"></a>Синтаксис

```
void __svm_vmrun(
   size_t VmcbPhysicalAddress
);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*VmcbPhysicalAddress*|[in] Физический адрес VMCB.|

## <a name="remarks"></a>Примечания

`__svm_vmrun` Функция использует минимальный объем сведений в VMCB, чтобы начать выполнение кода гостевой виртуальной машины. Используйте [__svm_vmsave](../intrinsics/svm-vmsave.md) или [__svm_vmload](../intrinsics/svm-vmload.md) работать, если вам требуется больше информации для обработки сложных прерывания или переключиться на другой виртуальной машины.

Функция `__svm_vmrun` эквивалентна инструкции компьютера `VMRUN` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: программирование,» номер документа 24593, редакция 3.11 и более поздних версиях в [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_vmrun`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_vmsave](../intrinsics/svm-vmsave.md)<br/>
[__svm_vmload](../intrinsics/svm-vmload.md)