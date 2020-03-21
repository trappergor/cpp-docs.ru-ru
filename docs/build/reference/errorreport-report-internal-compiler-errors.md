---
title: Параметр /errorReport (отчет о внутренних ошибках компилятора)
description: Справочник по параметру командной строкиC++ /ERRORREPORT для Microsoft C/Compiler.
ms.date: 02/09/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: 9efe96ed2611795e1fef408ad07b49d65261c3b1
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80075087"
---
# <a name="errorreport-report-internal-compiler-errors"></a>Параметр /errorReport (отчет о внутренних ошибках компилятора)

> [!NOTE]
> Параметр **/errorreport** является устаревшим. Начиная с Windows Vista, Управление отчетами об ошибках осуществляется с помощью параметров [отчеты об ошибках Windows (WER)](/windows/win32/wer/windows-error-reporting) .

## <a name="syntax"></a>Синтаксис

> **/errorreport:** \[**none** \| **Prompt** \| **очередь** \| **Send** ]

## <a name="remarks"></a>Примечания

Внутренняя ошибка компилятора (ICE) вызывается, когда компилятор не может обработать файл исходного кода. При возникновении внутренней ошибки компилятор не создает выходной файл или любую полезную диагностику, которую можно использовать для исправления кода.

Аргументы **/errorreport** переопределяются параметрами службы отчеты об ошибках Windows. Компилятор автоматически отправляет отчеты о внутренних ошибках в корпорацию Майкрософт, если отчетность включается отчеты об ошибках Windows. Если отключено отчеты об ошибках Windows, отчет не отправляется.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте страницу свойств **конфигурации** > **C/C++**  > **Дополнительные** свойства.

1. Измените свойство **отчет об ошибках** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.

## <a name="see-also"></a>См. также:

\ [параметров компилятора компилятором MSVC](compiler-options.md)
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
