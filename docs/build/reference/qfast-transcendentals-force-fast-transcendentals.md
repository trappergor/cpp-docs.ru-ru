---
title: /Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 383a915721d627367ca2ca035957df947996bbe2
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818353"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (принудительное использование быстрых трансцендентных функций)

Создает встроенный код для трансцендентных функций.

## <a name="syntax"></a>Синтаксис

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Примечания

Этот параметр компилятора заставляет трансцендентных функций для преобразования в встроенного кода для повышения быстродействия. Этот параметр действует только в том случае, когда используется вместе с **/fp: except** или **/fp: точное**. Создание встроенного кода для трансцендентных функций уже поведение по умолчанию в разделе **/fp:fast**.

Этот параметр несовместим с **/fp: strict**. См. в разделе [/fp (определение поведения с плавающей запятой)](fp-specify-floating-point-behavior.md) Дополнительные сведения о точке параметры компилятора.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /Q (низкоуровневые операции)](q-options-low-level-operations.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
