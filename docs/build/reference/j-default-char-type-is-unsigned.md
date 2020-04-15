---
title: /J (тип знака по умолчанию не подписан)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.DefaultCharIsUnsigned
- VC.Project.VCCLWCECompilerTool.DefaultCharIsUnsigned
- /j
helpviewer_keywords:
- defaults, char type
- char data type
- -J compiler option [C++]
- /J compiler option [C++]
- J compiler option [C++]
- default char type is unsigned
ms.assetid: 50973667-6638-491e-9c41-bff73acae19f
ms.openlocfilehash: 7bcf0f2eb2bef08757250999d0a6696b256fb15c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322199"
---
# <a name="j-default-char-type-is-unsigned"></a>/J (тип знака по умолчанию не подписан)

Изменяет `char` тип `signed char` по `unsigned char`умолчанию `char` от к, и тип с `int` нулевым расширением, когда он расширен до типа.

## <a name="syntax"></a>Синтаксис

```
/J
```

## <a name="remarks"></a>Remarks

Если `char` значение явно объявлено `signed`как, **опция /J** не влияет на него, и значение продлевается, когда оно расширено до `int` типа.

Параметр **/J** `_CHAR_UNSIGNED`определяет, который `#ifndef` используется в файле LIMITS.h для `char` определения диапазона типа по умолчанию.

ANSI C и СЗ не требуют конкретной реализации `char` типа. Эта опция полезна при работе с данными о персонажах, которые в конечном итоге будут переведены на язык, отличный от английского.

> [!NOTE]
> При использовании этой опции компилятора с ATL/MFC может быть сгенерирована ошибка. Хотя вы могли бы отключить `_ATL_ALLOW_CHAR_UNSIGNED`эту ошибку, определив, этот обходной путь не поддерживается и не всегда может работать.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. В **Solution Explorer**откройте меню ярлыка для проекта, а затем выберите **Свойства.**

1. В диалоговом поле **«Страницы свойств»** в левом стекле под **настройкой Свойства**расширьте **C/C,** а затем выберите **командную строку.**

1. В панели **дополнительных опций** укажите опцию **/J** компилятора.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DefaultCharIsUnsigned%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)<br/>
[Настройка свойств компилятора C++ и сборки в Visual Studio](../working-with-project-properties.md)
