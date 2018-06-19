---
title: COMM | Документы Microsoft
ms.custom: ''
ms.date: 05/22/2018
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
ms.openlocfilehash: 1df6c729ab130a7ff38d7f7cf83224e7425e7dba
ms.sourcegitcommit: da7b7533d1a4dc141cc0f09149e4e4196f2fe329
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/23/2018
ms.locfileid: "34463027"
---
# <a name="comm"></a>COMM

Создает переменную общих с атрибутами, заданными в *определение*.

## <a name="syntax"></a>Синтаксис

> **COMM** *определения* [, *определение*]...

## <a name="remarks"></a>Примечания

Общих переменных выделяются компоновщиком и не может быть инициализирован. Это означает, что не может зависеть расположение или последовательности таких переменных.

Каждый *определение* имеет следующий вид:

[*langtype*] [**NEAR** &#124; **ДАЛЬНЕГО**] _метка_**:**_тип_[**:**_число_]

Необязательный *langtype* задает имя, которое соответствует правилам именования. Он переопределяет любой язык, заданный параметром **. МОДЕЛЬ** директивы. Необязательный **NEAR** или **ДАЛЬНЕГО** переопределить текущей модели памяти. *Метка* имя переменной. *Тип* может быть любым описателем типа ([БАЙТОВ](../../assembler/masm/byte-masm.md), [WORD](../../assembler/masm/word.md)и так далее) или целое число, указывающее число байтов. Необязательный *число* указывает число элементов в объекте объявленных данных; значение по умолчанию — один.

## <a name="example"></a>Пример

В этом примере создается массив размером 512 БАЙТ элементов:

```masm
COMM FAR ByteArray:BYTE:512
```

## <a name="see-also"></a>См. также

[Справочник по директивам](../../assembler/masm/directives-reference.md)
