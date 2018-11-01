---
title: /WL (включение вывода однострочных диагностических сообщений)
ms.date: 11/04/2016
f1_keywords:
- /wl
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
ms.openlocfilehash: 2d2f3c1c7bac19fc0e401067f43e78e3770c6304
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428162"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (включение вывода однострочных диагностических сообщений)

Добавляет дополнительную информацию к ошибку или предупреждение.

## <a name="syntax"></a>Синтаксис

```
/WL
```

## <a name="remarks"></a>Примечания

Ошибки и предупреждения компилятора C++ может следовать дополнительную информацию, которая отображается по умолчанию в новой строке. При компиляции из командной строки, можно добавить дополнительную строку сведения ошибке или предупреждающее сообщение. Это может оказаться полезным, если записать выходные данные сборки в файл журнала, а затем обработать этот журнал, чтобы найти все ошибки и предупреждения. Точка с запятой будет отделить от дополнительной строки ошибка или предупреждение.

Не все ошибки и предупреждения имеют дополнительную строку данных. Следующий код приведет к ошибке, которое дополнительную строку данных; Это позволит проверить результат, при использовании **/WL**.

```
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

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