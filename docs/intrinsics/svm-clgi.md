---
title: __svm_clgi
ms.date: 11/04/2016
f1_keywords:
- __svm_clgi
helpviewer_keywords:
- CLGI instruction
- __svm_clgi intrinsic
ms.assetid: 6640f5ab-9472-46f9-a042-e15c4f1ff858
ms.openlocfilehash: fe25141499a19a265e2ac3ec746664ecd6cc9a2e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028701"
---
# <a name="svmclgi"></a>__svm_clgi

**Блок, относящийся только к системам Microsoft**

Очищает флаг глобального прерывания.

## <a name="syntax"></a>Синтаксис

```
void __svm_clgi( void );
```

## <a name="remarks"></a>Примечания

Функция `__svm_clgi` эквивалентна инструкции компьютера `CLGI` . Флаг прерывания глобального определяет микропроцессора игнорирует, откладывающий или обрабатывает прерывания из-за события, такие как завершение ввода/вывода, температуры оповещение оборудования или исключение отладки.

Эта функция поддерживает взаимодействие монитора виртуальной машины узла с гостевой операционной системой и ее приложениями. Дополнительные сведения см. в документе «архитектуре AMD64 для программистов вручную том 2: Номер 24593, редакция 3.11, System Programming,» документа в [AMD corporation](https://developer.amd.com/resources/developer-guides-manuals/) сайта.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__svm_clgi`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__svm_stgi](../intrinsics/svm-stgi.md)