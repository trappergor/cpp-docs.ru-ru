---
title: /ERRORREPORT (создание отчетов о внутренних ошибках компоновщика)
description: Узнайте, как использовать/ЕРРОРРЕПОРТ.
ms.date: 02/09/2020
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
ms.openlocfilehash: 7d16904da8490018235278347f23e37339739415
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742740"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (создание отчетов о внутренних ошибках компоновщика)

Параметр **/errorreport** является устаревшим. Начиная с Windows Vista, Управление отчетами об ошибках осуществляется с помощью параметров [отчеты об ошибках Windows (WER)](/windows/win32/wer/windows-error-reporting) .

## <a name="syntax"></a>Синтаксис

> **/Errorreport:** \[ **нет** \| **запрос** \| **очередь** \| **Отправить** ]

## <a name="remarks"></a>Remarks

Аргументы **/errorreport** переопределяются параметрами службы отчеты об ошибках Windows. Компоновщик автоматически отправляет отчеты о внутренних ошибках в корпорацию Майкрософт, если отчетность включается отчеты об ошибках Windows. Если отключено отчеты об ошибках Windows, отчет не отправляется.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Окна свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойств сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте **Configuration Properties**  >  **Linker**  >  страницу свойств "**Дополнительные** свойства" компоновщика свойств конфигурации.

1. Измените свойство **отчет об ошибках** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику КОМПИЛЯТОРОМ MSVC](linking.md)\
[Параметры компоновщика MSVC](linker-options.md)
