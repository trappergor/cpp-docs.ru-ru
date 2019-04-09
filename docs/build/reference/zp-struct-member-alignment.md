---
title: /Zp (Выравнивание члена структуры)
ms.date: 04/04/2019
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
ms.openlocfilehash: d76cd93c7af4228bff8f73fa3bcbf40fa149b0be
ms.sourcegitcommit: 35c4b3478f8cc310ebbd932a18963ad8ab846ed9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59237168"
---
# <a name="zp-struct-member-alignment"></a>/Zp (Выравнивание члена структуры)

Элементы управления как члены структуры, упакованы в памяти и определяет тот же способ упаковки для всех структур в модуле.

## <a name="syntax"></a>Синтаксис

> **/Zp**[**1**|**2**|**4**|**8** | **16**]

## <a name="remarks"></a>Примечания

**/Zp**_n_ указывает компилятору где хранить каждый элемент структуры. Компилятор сохраняет элементы после первого на границе, которая является наименьшее значение размера типа, или *n*-байтовой границе.

В следующей таблице описаны доступные упаковки значения:

|Аргумент/Zp|Действие|
|-|-|
|1|Упаковывает структуры в 1 байт. Совпадение с кодом **/Zp**.|
|2|Упаковывает структуры в 2-байтовым границам.|
|4|Упаковывает структуры в 4-байтовым границам.|
|8|Упаковывает структуры в 8-байтное (по умолчанию для x86, ARM и ARM64).|
|16| Упаковывает структуры в 16-байтовым границам (по умолчанию для x64).|

Не используйте этот параметр, если у вас нет специальных требований к выравниванию.

> [!WARNING]
> Задать заголовки C++ в пакете SDK для Windows и предполагается, **/zp8** упаковки внутренним образом. Может произойти повреждение памяти **/Zp** параметр изменяется внутри заголовков Windows SDK. Заголовки не будут затронуты **/Zp** параметр установлен в командной строке.

Можно также использовать [пакет](../../preprocessor/pack.md) для упаковка структур управления. Дополнительные сведения о выравнивании см. в разделах:

- [align](../../cpp/align-cpp.md)

- [Оператор __alignof](../../cpp/alignof-operator.md)

- [__unaligned](../../cpp/unaligned.md)

- [/ALIGN (выравнивание разделов)](align-section-alignment.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **создание кода** страницу свойств.

1. Изменить **выравнивание членов структур** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StructMemberAlignment%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md) \
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
