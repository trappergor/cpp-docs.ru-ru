---
title: /Qvec-report (уровень отчетности автоматического векторизатора)
ms.date: 11/04/2016
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
ms.openlocfilehash: 260cf89d50110f960eb6f320dccbb4a1d80f65bc
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373818"
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (уровень отчетности автоматического векторизатора)

Включает функцию отчетов компилятора [Auto-векторизатора](../../parallel/auto-parallelization-and-auto-vectorization.md) и задает уровень информационных сообщений для вывода во время компиляции.

## <a name="syntax"></a>Синтаксис

```
/Qvec-report:{1}{2}
```

## <a name="remarks"></a>Remarks

**/Qvec-report: 1**<br/>
Выводит информационное сообщение для циклов, которые являются векторными.

**/Qvec-report: 2**<br/>
Выводит информационное сообщение для циклов, которые являются векторными, и для циклов, которые не векторны, а также с кодом причины.

Сведения о кодах причин и сообщениях см. в разделе [сообщения векторизатора и параллелизатора](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).

### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Установка параметра компилятора/Qvec-report в Visual Studio

1. В области **Обозреватель решений**откройте контекстное меню для проекта и выберите пункт **Свойства**.

1. В диалоговом окне **страницы свойств** в разделе **C/C++** выберите пункт **Командная строка**.

1. В поле **Дополнительные параметры** введите `/Qvec-report:1` или `/Qvec-report:2` .

### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>Установка параметра компилятора/Qvec-report программным способом

- Используйте пример кода в <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры/q (низкоуровневые операции)](q-options-low-level-operations.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора КОМПИЛЯТОРОМ MSVC](compiler-command-line-syntax.md)<br/>
[Вектор машинного кода в Visual Studio](https://docs.microsoft.com/archive/blogs/nativeconcurrency/auto-vectorizer-in-visual-studio-2012-overview)
