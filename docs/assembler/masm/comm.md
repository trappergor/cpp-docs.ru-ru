---
title: COMM | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- COMM
dev_langs:
- C++
helpviewer_keywords:
- COMM directive
ms.assetid: a23548c4-ad04-41fa-91da-945f228de742
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 87bf6d91de052d7ecaf637100b455e66819c748b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690036"
---
# <a name="comm"></a>COMM

Создание общей переменной с атрибутами, заданными в *определение*.

## <a name="syntax"></a>Синтаксис

> **COMM** *определение* [, *определение*]...

## <a name="remarks"></a>Примечания

Общих переменных выделяются компоновщиком и не может быть инициализирован. Это означает, что вы не может зависеть от расположения или последовательности таких переменных.

Каждый *определение* имеет следующий вид:

[*langtype*] [**NEAR** &#124; **FAR**] _метка_**:**_тип_[**:**_число_]

Необязательный *langtype* задает соглашения об именовании для него имя. Этот параметр переопределяет любой язык, заданный параметром **. МОДЕЛЬ** директива. Необязательный **NEAR** или **FAR** переопределить текущей модели памяти. *Метка* имя переменной. *Тип* может быть любым описателем типа ([БАЙТОВ](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md), и так далее) или целое число, указывающее число байтов. Необязательный *число* указывает число элементов в объекте объявленный данных; значение по умолчанию — один.

## <a name="example"></a>Пример

В этом примере создает массив из элементов 512 БАЙТ:

```asm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)<br/>
