---
title: Указание пути | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- names [C++], compiler output files
- cl.exe compiler, output files
- output files, specifying pathnames
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 636326e5af577b4e26c61a2094fe73dd4a680f2d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402477"
---
# <a name="specifying-the-pathname"></a>Указание пути

Каждый параметр выходного файла принимает *pathname* аргумент, который можно указать расположение и имя выходного файла. Аргумент может включать имя диска, каталог и имя файла. Не должно быть пробела между параметром и аргумента.

Если *pathname* включает имя файла без расширения, компилятор выдает выходные данные расширение по умолчанию. Если *pathname* включает каталог, но без имени файла, компилятор создает файл с именем по умолчанию в указанном каталоге. Имя по умолчанию основан на базовое имя исходного файла и расширение по умолчанию на основе типа выходного файла. Если вы не указываете *pathname* полностью, компилятор создает файл с именем по умолчанию в каталоге по умолчанию.

Кроме того *pathname* аргументом может быть имя устройства (AUX, CON, PRN или NUL), а не именем файла. Не используйте пробел между параметром и имя устройства или двоеточия как часть имени устройства.

|Имя устройства|Представляет|
|-----------------|----------------|
|AUX|Дополнительное устройство|
|CON|Консоль|
|PRN|Принтер|
|NUL|NULL-устройство (файл не создается)|

## <a name="example"></a>Пример

Следующая командная строка отправляет файл сопоставления для принтера:

```
CL /FmPRN HELLO.CPP
```

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](../../build/reference/output-file-f-options.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)