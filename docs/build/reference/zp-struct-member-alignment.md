---
title: /Zp (Выравнивание члена структуры)
ms.date: 12/17/2018
f1_keywords:
- /zp
- VC.Project.VCCLCompilerTool.StructMemberAlignment
- VC.Project.VCCLWCECompilerTool.StructMemberAlignment
helpviewer_keywords:
- Struct Member Alignment compiler option
- Zp compiler option
- /Zp compiler option [C++]
- -Zp compiler option [C++]
ms.assetid: 5242f656-ed9b-48a3-bc73-cfcf3ed2520f
ms.openlocfilehash: d1821d8dc5eab202a918893a1e7895151629b551
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627531"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Выравнивание члена структуры)

Элементы управления как члены структуры, упакованы в памяти и определяет тот же способ упаковки для всех структур в модуле.

## <a name="syntax"></a>Синтаксис

> **/Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Примечания

При указании **/Zp**_n_ параметр, каждый элемент структуры после первого хранится на размер типа или *n*-байтовым границам (где *n* равен 1, 2, 4, 8 или 16), какое значение меньше.

В следующей таблице описаны доступные упаковки значения:

|Аргумент/Zp|Действие|
|-|-|
|1|Упаковывает структуры в 1 байт. Совпадение с кодом **/Zp**.|
|2|Упаковывает структуры в 2-байтовым границам.|
|4|Упаковывает структуры в 4-байтовым границам.|
|8|Упаковывает структуры в 8-байтное (по умолчанию).|
|16| Упаковывает структуры в 16-байтовым границам.|

Не следует использовать этот параметр, если у вас нет специальных требований к выравниванию.

> [!WARNING]
> Заголовки C++ в пакете Windows SDK предполагается **/zp8** упаковки. Может произойти повреждение памяти **/Zp** параметр изменяется при использовании заголовков Windows SDK.

Можно также использовать [пакет](../../preprocessor/pack.md) для упаковка структур управления. Дополнительные сведения о выравнивании см. в разделах:

- [align](../../cpp/align-cpp.md)

- [Оператор __alignof](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [Примеры выравнивания структуры](../../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 конкретных)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **C/C++** > **создание кода** страницу свойств.

1. Изменить **выравнивание членов структур** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>См. также

- [Параметры компилятора](../../build/reference/compiler-options.md)
- [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
