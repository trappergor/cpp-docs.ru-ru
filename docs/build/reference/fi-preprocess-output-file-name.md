---
title: /Fi (предварительная обработка имени выходного файла)
ms.date: 11/04/2016
f1_keywords:
- /Fi
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
ms.openlocfilehash: 02d2a27f0a3d6b6aee6c2cd6f7161c9de718446d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414034"
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (предварительная обработка имени выходного файла)

Задает имя выходного файла, к которому [/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md) параметр компилятора записывает предварительно обработанные выходные данные.

## <a name="syntax"></a>Синтаксис

```
/Fipathname
```

#### <a name="parameters"></a>Параметры

|Параметр|Описание:|
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
[/P (вывод результатов предварительной обработки в файл)](../../build/reference/p-preprocess-to-a-file.md)<br/>
[Указание пути](../../build/reference/specifying-the-pathname.md)
