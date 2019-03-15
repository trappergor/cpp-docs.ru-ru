---
title: /GF (Исключение повторяющихся строк)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.StringPooling
- VC.Project.VCCLWCECompilerTool.StringPooling
- /gf
helpviewer_keywords:
- duplicate strings
- Eliminate Duplicate Strings compiler option [C++]
- pooling strings compiler option [C++]
- -GF compiler option [C++]
- /GF compiler option [C++]
- GF compiler option [C++]
- strings [C++], pooling
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
ms.openlocfilehash: 2f2bec446fcec522857b4c05a34311e6c26c9b75
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812321"
---
# <a name="gf-eliminate-duplicate-strings"></a>/GF (Исключение повторяющихся строк)

Позволяет компилятору создавать одну копию одинаковых строк в образе программы и в памяти во время выполнения. Это такая оптимизация называется *объединение строк* , можно создать небольшие программы.

## <a name="syntax"></a>Синтаксис

```
/GF
```

## <a name="remarks"></a>Примечания

Если вы используете **/GF**, операционная система не меняет местами часть памяти, строки и может считывать строки обратно из файла образа.

**/GF** пулы строк только для чтения. При попытке изменить строки в **/GF**, возникает сообщение об ошибке приложения.

Объединение строк позволяет назначить несколько указателей на несколько буферов быть нескольких указателей на один буфер. В следующем коде `s` и `t` инициализируются с этой же строкой. Объединение строк вызывает указатель на ту же память.

```
char *s = "This is a character buffer";
char *t = "This is a character buffer";
```

> [!NOTE]
>  [/ZI](z7-zi-zi-debug-information-format.md) автоматически задает режим работы, изменить и продолжить, **/GF** параметр.

> [!NOTE]
>  **/GF** параметр компилятора создает адресуемый раздел для каждого уникальную строку. И по умолчанию объектный файл может содержать до 65 536 адресуемых секций. Если программа содержит более 65 536 строк, используйте [/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md) параметр компилятора, чтобы создать дополнительные разделы.

**/GF** вступает в силу, когда [/O1](o1-o2-minimize-size-maximize-speed.md) или **/O2** используется.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **создание кода** страницу свойств.

1. Изменить **включить объединение строк** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
