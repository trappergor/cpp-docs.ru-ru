---
title: /GZ (Позволяет проверку фрейма стека ошибки во время выполнения)
ms.date: 11/04/2016
f1_keywords:
- /gz
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
ms.openlocfilehash: 35475b87b8f59fbb0fb24e62690f8fc24c7cb4e9
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423473"
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Позволяет проверку фрейма стека ошибки во время выполнения)

Выполняет те же операции [/RTC (проверки ошибок во время выполнения)](../../build/reference/rtc-run-time-error-checks.md) параметр. Не рекомендуется.

## <a name="syntax"></a>Синтаксис

```
/GZ
```

## <a name="remarks"></a>Примечания

**/GZ** предназначен только для использования в неоптимизированном ([/Od (Выключение (отладчика))](../../build/reference/od-disable-debug.md)) сборки.

**/GZ** является устаревшим начиная с Visual Studio 2005; используйте [/RTC (проверки ошибок во время выполнения)](../../build/reference/rtc-run-time-error-checks.md) вместо этого. Список параметров компилятора, см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).

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
