---
title: '@ (указать файл ответа компилятора)'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: c2b5578e1ce1db590bdf5abbff0c91e858803ad7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273006"
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

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
