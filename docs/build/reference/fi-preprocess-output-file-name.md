---
title: -Fi (Предварительная обработка имени выходного файла) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Fi
dev_langs:
- C++
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfe9e54dbafbcbd27763060dc9d81b21bac2503d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709407"
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (предварительная обработка имени выходного файла)

Задает имя выходного файла, к которому [/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md) параметр компилятора записывает предварительно обработанные выходные данные.

## <a name="syntax"></a>Синтаксис

```
/Fipathname
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание|
|---------------|-----------------|
|`pathname`|Имя и путь выходного файла, созданного **/P** параметр компилятора.|

## <a name="remarks"></a>Примечания

Используйте **/Fi** параметр компилятора в сочетании с **/P** параметр компилятора.

Если указывается только путь для `pathname` параметр, базовое имя исходного файла используется в качестве базового имени файла предварительно обработанные выходные данные. `pathname` Параметра не требуется расширение имени определенного файла. Тем не менее если не указать расширение имени файла, используется расширение «i».

## <a name="example"></a>Пример

Следующая командная строка предварительно обрабатывает PROGRAM.cpp, сохраняет комментарии, добавляет [#line](../../preprocessor/hash-line-directive-c-cpp.md) директивы и записывает результат в файл MYPROCESS.i.

```
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[/P (вывод результатов предварительной обработки файла)](../../build/reference/p-preprocess-to-a-file.md)
[указание пути](../../build/reference/specifying-the-pathname.md)