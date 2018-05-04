---
title: '/ Zc: wchar_t (wchar_t – это собственный тип) | Документы Microsoft'
ms.custom: ''
ms.date: 03/01/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.TreatWChar_tAsBuiltInType
- VC.Project.VCCLCompilerTool.TreatWChar_tAsBuiltInType
- /Zc:wchar_t
dev_langs:
- C++
helpviewer_keywords:
- /Zc compiler options [C++]
- -Zc compiler options [C++]
- wchar_t type
- Conformance compiler options
- Zc compiler options [C++]
ms.assetid: b0de5a84-da72-4e5a-9a4e-541099f939e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 061aa4a70412a0b51450470e690bea5633b764ad
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t – это собственный тип)

Разбор `wchar_t` как встроенного типа в соответствии со стандартом C++.

## <a name="syntax"></a>Синтаксис

> **/Zc:wchar_t**[**-**]

## <a name="remarks"></a>Примечания

Если **/Zc: wchar_t** , `wchar_t` — это ключевое слово для встроенного целочисленного типа в коде, скомпилированном как C++. Если **/Zc:wchar_t-** (со знаком минус) указанного, или код компилируется как C, `wchar_t` не является встроенным типом. Вместо этого `wchar_t` определяется как `typedef` для `unsigned short` в канонической заголовок stddef.h. (Реализация Майкрософт определяет его в другой заголовок, включенный путем stddef.h и других стандартных заголовков.)

Мы не рекомендуем **/Zc:wchar_t-** поскольку стандарт C++ требует, `wchar_t` быть встроенным типом. Использование версии `typedef` может вызывать проблемы переносимости. Если обновление с предыдущих версий Visual C++ и возникает ошибка компилятора [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) потому, что код пытается выполнить неявное преобразование `wchar_t` для `unsigned short`, мы рекомендуем изменить код, чтобы устранить ошибку, вместо параметра **/Zc:wchar_t-**.

**/Zc: wchar_t** параметр по умолчанию в компиляций C++ и учитывается в компиляциях C. [/ Разрешительным-](permissive-standards-conformance.md) параметр не влияет на **/Zc: wchar_t**.

Microsoft реализует тип `wchar_t` как двухбайтовое значение без знака. Он сопоставляется с типом собственного специфичные для Microsoft `__wchar_t`. Дополнительные сведения о `wchar_t`, в разделе [диапазоны типов данных](../../cpp/data-type-ranges.md) и [базовые типы](../../cpp/fundamental-types-cpp.md).

При написании нового кода, который должен взаимодействовать со старым кодом, который по-прежнему использует `typedef` версии `wchar_t`, создайте перегруженные версии для обоих `unsigned short` и `__wchar_t` различные виды `wchar_t`, чтобы код можно связать с код компилируется с **/Zc: wchar_t** или код, скомпилированный без него. В противном случае будет необходимо предоставить две различных сборки библиотеки: с и без **/Zc: wchar_t** включена. Даже в этом случае рекомендуется произвести сборку старого кода с использованием компилятора, который используется для компиляции нового кода. Никогда не смешивайте двоичные файлы, скомпилированные разными компиляторами.

Когда **/Zc: wchar_t** указано,  **\_WCHAR\_T\_ОПРЕДЕЛЕННЫЕ** и  **\_СОБСТВЕННОГО\_WCHAR\_T\_ОПРЕДЕЛЕННЫЕ** определенные символы. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md).

Если ваш код использует глобальные функции COM компилятора, потому что **/Zc: wchar_t** теперь на по умолчанию, мы рекомендуем изменить явные ссылки на comsupp.lib (из [комментарий pragma](../../preprocessor/comment-c-cpp.md) или на командной строки) ссылками на comsuppw.lib или comsuppwd.lib. (Если необходимо выполнять компиляцию с **/Zc:wchar_t-**, используйте comsupp.lib.) Если включен файл заголовка comdef.h, правильная библиотека задается автоматически. Сведения о модели COM в компиляторе см. в разделе [поддержки компилятора COM](../../cpp/compiler-com-support.md).

`wchar_t` Встроенного типа не поддерживается при компиляции кода C. Дополнительные сведения о вопросах соответствия в Visual C++ см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **языка** страницы.

1. Изменить **считать wchar_t встроенным типом** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.

## <a name="see-also"></a>См. также

[/Zc (соответствие)](../../build/reference/zc-conformance.md)<br/>
