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
ms.openlocfilehash: b1ded1cd18eb75ed47b76c1353ad82a7fa497ba9
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988564"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (включение вывода однострочных диагностических сообщений)

Добавляет дополнительные сведения к сообщению об ошибке или предупреждению.

## <a name="syntax"></a>Синтаксис

```
/WL
```

## <a name="remarks"></a>Заметки

За сообщениями об ошибках C++ и предупреждениями компилятора могут следовать дополнительные сведения, которые по умолчанию отображаются в новой строке. При компиляции из командной строки можно добавить дополнительную строку данных к сообщению об ошибке или предупреждению. Это может быть желательным, если вы собираете выходные данные сборки в файл журнала, а затем обрабатываете этот журнал для поиска всех ошибок и предупреждений. Точка с запятой будет отделять сообщение об ошибке или предупреждение от дополнительной строки.

Не все сообщения об ошибках и предупреждениях имеют дополнительную строку информации. Следующий код выдаст ошибку с дополнительной строкой данных. Это позволит проверить результат при использовании **/WL**.

```cpp
// compiler_option_WL.cpp
// compile with: /WL
#include <queue>
int main() {
   std::queue<int> q;
   q.fromthecontinuum();   // C2039
}
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также:

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
