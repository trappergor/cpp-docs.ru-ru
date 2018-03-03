---
title: "-Zc: wchar_t (wchar_t – это собственный тип) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3375e39120fdc8f2b0d8d5502aa6def997511ff5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zcwchart-wchart-is-native-type"></a>/Zc:wchar_t (wchar_t – это собственный тип)
Разбор `wchar_t` как встроенного типа в соответствии со стандартом C++. По умолчанию **/Zc: wchar_t** включен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zc:wchar_t[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Если **/Zc: wchar_t** , `wchar_t` сопоставляется с типом собственного специфичные для Microsoft `__wchar_t`. Если **/Zc:wchar_t-** указано (со знаком минус) `wchar_t` сопоставляется `typedef` для `unsigned short`. (В Visual C++ 6.0 и ранее тип `wchar_t` не был реализован как встроенный тип, а объявлялся в файле wchar.h как `typedef` для `unsigned short`.) Мы не рекомендуем **/Zc:wchar_t-** поскольку стандарт C++ требует, `wchar_t` быть встроенным типом. Использование версии `typedef` может вызывать проблемы переносимости. Если обновление с предыдущих версий Visual C++ и возникает ошибка компилятора [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) потому, что код пытается выполнить неявное преобразование `wchar_t` для `unsigned short`, мы рекомендуем изменить код, чтобы устранить ошибку, вместо параметра **/Zc:wchar_t-**.  
  
 Microsoft реализует тип `wchar_t` как двухбайтовое значение без знака. Дополнительные сведения о `wchar_t`, в разделе [диапазоны типов данных](../../cpp/data-type-ranges.md) и [базовые типы](../../cpp/fundamental-types-cpp.md).  
  
 При написании нового кода, который должен взаимодействовать со старым кодом, который по-прежнему использует `typedef` версии `wchar_t`, создайте перегруженные версии для обоих `unsigned short` и `__wchar_t` различные виды `wchar_t`, чтобы код можно связать с код компилируется с **/Zc: wchar_t** или код, скомпилированный без него. В противном случае будет необходимо предоставить две различных сборки библиотеки — одну с **/Zc: wchar_t** включена. Даже в этом случае рекомендуется произвести сборку старого кода с использованием компилятора, который используется для компиляции нового кода. Никогда не смешивайте двоичные файлы, скомпилированные разными компиляторами.  
  
 Когда **/Zc: wchar_t** указано, **_WCHAR_T_DEFINED** и **_NATIVE_WCHAR_T_DEFINED** определенные символы. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md).  
  
 Если ваш код использует глобальные функции COM компилятора, потому что **/Zc: wchar_t** теперь на по умолчанию, мы рекомендуем изменить явные ссылки на comsupp.lib—from [комментарий pragma](../../preprocessor/comment-c-cpp.md) или команды Строка, ссылками на comsuppw.lib или comsuppwd.lib. (Если необходимо выполнять компиляцию с **/Zc:wchar_t-**, используйте comsupp.lib.) Если включен файл заголовка comdef.h, правильная библиотека задается автоматически. Сведения о модели COM в компиляторе см. в разделе [поддержки компилятора COM](../../cpp/compiler-com-support.md).  
  
 При компиляции кода C тип `wchar_t` не поддерживается. Дополнительные сведения о вопросах соответствия в Visual C++ см. в разделе [нестандартное поведение](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  В левой области разверните **свойства конфигурации**, **C/C++**, а затем выберите **языка**.  
  
3.  Изменить **считать wchar_t встроенным типом** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.TreatWChar_tAsBuiltInType%2A>.  
  
## <a name="see-also"></a>См. также  
 [/Zc (соответствие)](../../build/reference/zc-conformance.md)