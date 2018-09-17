---
title: '@ (Указать файл ответа компилятора) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '@'
dev_langs:
- C++
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c86d49aea2ce7a8d8b438c64cd883b71e5a4646
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720854"
---
# <a name="-specify-a-compiler-response-file"></a>@ (указать файл ответа компилятора)

Указывает файл ответа компилятора.

## <a name="syntax"></a>Синтаксис

> **\@**<em>response_file</em>

## <a name="arguments"></a>Аргументы

*response_file*<br/>
Текстовый файл, содержащий команды для компилятора.

## <a name="remarks"></a>Примечания

Файл ответов может содержать любые команды, следует указать в командной строке. Это может быть полезно в том случае, если аргументы командной строки превышает 127 символов.

Невозможно указать **\@** параметр в файле ответов. То есть файл ответов не может включать другой файл ответа.

Из командной строки можно указать любое количество параметров файла ответов (например, `@respfile.1 @respfile.2`) как требуется.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

- Файл ответов не может быть из среды разработки и должен быть указан в командной строке.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- Этот параметр не может изменяться программно.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
