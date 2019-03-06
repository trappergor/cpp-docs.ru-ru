---
title: /Zs (Только синтаксическая проверка)
ms.date: 11/04/2016
f1_keywords:
- /zs
helpviewer_keywords:
- -Zs compiler option [C++]
- Syntax Check Only compiler option
- Zs compiler option
- /Zs compiler option [C++]
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
ms.openlocfilehash: c7c8993ba9589b2a5fbc59d67e8603c141511695
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413320"
---
# <a name="zs-syntax-check-only"></a>/Zs (Только синтаксическая проверка)

Указывает компилятору проверять только синтаксис исходных файлов в командной строке.

## <a name="syntax"></a>Синтаксис

```
/Zs
```

## <a name="remarks"></a>Примечания

При использовании этого параметра, не выходные файлы создаются и сообщения об ошибках записываются в стандартный вывод.

**/Zs** параметр позволяет быстро находить и исправлять ошибки синтаксиса, перед компиляцией и связать файл с исходным.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
