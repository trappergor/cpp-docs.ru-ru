---
title: __svm_invlpga
ms.date: 11/04/2016
f1_keywords:
- __svm_invlpga
helpviewer_keywords:
- __svm_invlpga intrinsic
- INVLPGA instruction
ms.assetid: aa6578ce-8278-464b-8815-a0fc45330915
ms.openlocfilehash: 5e470fc12ad47aa156c513b293543fa356398d5e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390273"
---
# <a name="svminvlpga"></a>__svm_invlpga

**Блок, относящийся только к системам Microsoft**

Запись сопоставления адресов в буфере ассоциативные перевода компьютера не делает недействительными. Параметры определяют виртуальный адрес и адрес места идентификатор страницы, чтобы сделать недействительным.

## <a name="syntax"></a>Синтаксис

```
void __svm_invlpga(void *Va, int ASID);
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|*VA*|[in] Виртуальный адрес страницы, чтобы сделать недействительным.|
|*ASID*|[in] Адрес места идентификатор (ASID) страницы, чтобы сделать недействительным.|

## <a name="remarks"></a>Примечания

Функция `__svm_invlpga` эквивалентна инструкции компьютера `INVLPGA` . Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: Номер 24593, редакция 3.11, System Programming,» документа в [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_invlpga`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)