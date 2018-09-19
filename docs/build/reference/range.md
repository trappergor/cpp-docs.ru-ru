---
title: — ДИАПАЗОН | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /RANGE
dev_langs:
- C++
helpviewer_keywords:
- /RANGE dumpbin option
- -RANGE dumpbin option
ms.assetid: 7eeba266-32be-49cc-a350-96bdf541f98a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e7525b8c1872616182141d624bff8f94571952
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712196"
---
# <a name="range"></a>Параметр /RANGE

Изменяет вывод свойства (программа DUMPBIN) при использовании с другими параметрами (программа DUMPBIN), например/RAWDATA или/DISASM.

## <a name="syntax"></a>Синтаксис

```
/RANGE:vaMin[,vaMax]
```

## <a name="parameters"></a>Параметры

*vaMin*<br/>
Виртуальный адрес, в которой необходимо начать операцию (программа DUMPBIN).

*vaMax*<br/>
(Необязательно) Виртуальный адрес, по которому вы не хотите dumpbin для завершения. Если не указан, dumpbin перейдет в конец файла.

## <a name="remarks"></a>Примечания

Чтобы просмотреть виртуальные адреса образа, используйте файл сопоставления для образа (RVA + Base), **/DISASM** или **/Headers** параметр (программа DUMPBIN), или Дизассемблированный код в отладчике Visual Studio.

## <a name="example"></a>Пример

В этом примере **/диапазон** используется для изменения отображения **/DISASM** параметр. В этом примере начальное значение выражается как десятичное число, и конечное значение указывается в виде шестнадцатеричного числа.

```
dumpbin /disasm /range:4219334,0x004061CD t.exe
```

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)