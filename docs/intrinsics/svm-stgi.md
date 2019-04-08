---
title: __svm_stgi
ms.date: 11/04/2016
f1_keywords:
- __svm_stgi
helpviewer_keywords:
- __svm_stgi intrinsic
- STGI instruction
ms.assetid: 96488da4-5587-4e99-8674-627a9e51be84
ms.openlocfilehash: ea138f17a24af21afa937991f77bd1e2a689c3f7
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024794"
---
# <a name="svmstgi"></a>__svm_stgi

**Блок, относящийся только к системам Microsoft**

Задает флаг глобального прерывания.

## <a name="syntax"></a>Синтаксис

```
void __svm_stgi(void);
```

## <a name="remarks"></a>Примечания

Функция `__svm_stgi` эквивалентна инструкции компьютера `STGI` . Флаг прерывания глобального определяет микропроцессора игнорирует, откладывающий или обрабатывает прерывания из-за события, такие как завершение ввода/вывода, температуры оповещение оборудования или исключение отладки.

Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: Номер 24593, редакция 3.11, System Programming,» документа в [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_stgi`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_clgi](../intrinsics/svm-clgi.md)