---
title: -Zp (выравнивание члена структуры) | Документы Microsoft
ms.custom: ''
ms.date: 04/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
dev_langs:
- C++
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1666da40f748d18c762eae19595692addcdbf78a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="zp-struct-member-alignment"></a>/Zp (Выравнивание члена структуры)

Определяет, как члены структуры упакованы в памяти и определяет тот же способ упаковки для всех структур в модуле.

## <a name="syntax"></a>Синтаксис

> **/Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Примечания

При указании **/Zp**_n_ параметра, каждый элемент структуры после первого хранится на размер типа члена или *n*-байтовым границам (где *n* — 1, 2, 4, 8 или 16), какое значение меньше.

В следующей таблице описаны доступные упаковки значения:

|/Zp аргумент|Действие|
|-|-|
|1|Упаковывает структуры в 1 байт. То же, что **/Zp**.|
|2|Упаковывает структуры в 2 байта.|
|4|Упаковывает структуры в 4-байтовым границам.|
|8|Упаковывает структуры в 8-байтовым границам (по умолчанию).|
|16| Упаковывает структуры в 16-байтовым границам.|

Не следует использовать этот параметр, если у вас нет специальных требований к выравниванию.

> [!WARNING]  
> Предположим, заголовки C++ в Windows SDK **/zp8** упаковки. Может произойти повреждение памяти **/Zp** параметр изменяется, когда использование заголовков Windows SDK.

Можно также использовать [пакет](../../preprocessor/pack.md) упаковки структуры элемента управления. Дополнительные сведения о выравнивании см. в разделах:

- [align](../../cpp/align-cpp.md)

- [Оператор __alignof](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [Примеры выравнивания структуры](../../build/examples-of-structure-alignment.md) (x64 64)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **C/C++** > **создания кода** страницу свойств.

1. Изменить **выравнивание члена структуры** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>См. также

- [Параметры компилятора](../../build/reference/compiler-options.md)   
- [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
