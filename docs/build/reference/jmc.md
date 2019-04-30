---
title: / JMC (отлаживать только мой код)
ms.date: 08/20/2018
f1_keywords:
- /JMC
helpviewer_keywords:
- /JMC compiler option [C++]
- Just my code [C++]
- -JMC compiler option [C++]
- User code, debugging
- JMC compiler option [C++]
ms.openlocfilehash: c107ad7107d2a65ed19719933aa127c0557916ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291643"
---
# <a name="jmc-just-my-code-debugging"></a>/ JMC (отлаживать только мой код)

Задает поддержку компилятора для собственных *Just My Code* отладки в отладчике Visual Studio. Этот параметр поддерживает параметры пользователя, которые позволяют Visual Studio выполните шаг с обходом системы, платформы, библиотеки и другие вызовы, не написанный пользователем, а также свернуть такие вызовы в окна стека вызова. **/JMC** параметр компилятора доступен, начиная с Visual Studio 2017 версии 15.8.

## <a name="syntax"></a>Синтаксис

> **/JMC**\[**-**]

## <a name="remarks"></a>Примечания

В Visual Studio [Just My Code](/visualstudio/debugger/just-my-code) параметры определяют, будет ли отладчик Visual Studio обойдет системы, платформы, библиотеки и другие вызовы, не написанный пользователем. **/JMC** параметр компилятора включает поддержку отлаживать только мой код в машинном коде C++. Когда **/JMC** будет включен, компилятор вставляет вызовы во вспомогательную функцию `__CheckForDebuggerJustMyCode`, в прологе функции. Вспомогательная функция предоставляет обработчики, которые поддерживают операции шаг Just My Code отладчика Visual Studio. Чтобы включить только мой код в отладчике Visual Studio в строке меню выберите **средства** > **параметры**, а затем задайте для параметра в **Отладка**  >  **Общие** > **включить только мой код**.

**/JMC** параметр требует, что ваш код ссылки для среды выполнения библиотеки CRT (C), который предоставляет `__CheckForDebuggerJustMyCode` вспомогательную функцию. Если проект не содержит ссылок на CRT, может появиться сообщение об ошибке компоновщика **LNK2019: неразрешенные внешний символ __CheckForDebuggerJustMyCode**. Чтобы устранить эту ошибку, либо ссылается на CRT, либо отключить **/JMC** параметр.

По умолчанию **/JMC** компилятора выключен. Тем не менее начиная с версии Visual Studio 2017 версии 15.8 этот параметр включен в большинство шаблонов проектов Visual Studio. Чтобы явно отключить этот параметр, используйте **/JMC-** параметр в командной строке. В Visual Studio откройте диалоговое окно страницы свойств проекта и измените **поддержки только мой код отладки** свойство в **свойства конфигурации** > **C/C++**  >  **Общие** страницу свойств для **нет**.

Дополнительные сведения см. в разделе [C++ Just My Code](/visualstudio/debugger/just-my-code#BKMK_C___Just_My_Code) в [укажите, следует ли отладка пользовательского кода, с помощью "только мой код" в Visual Studio](/visualstudio/debugger/just-my-code)и в блоге команды разработчиков Visual C++, посвященной [объявляет о C++ только мой код Шаг с заходом в Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2018/06/29/announcing-jmc-stepping-in-visual-studio/).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **Общие** страницу свойств.

1. Изменить **поддержки только мой код отладки** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
