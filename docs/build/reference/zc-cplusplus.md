---
title: /Zc:__cplusplus (включить обновленный макрос __cplusplus)
ms.date: 05/16/2019
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 43392438eabc7cc7f6decb1349d112a0ce5bd0f5
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837549"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc:__cplusplus (включить обновленный макрос __cplusplus)

При указании параметра компилятора **/Zc:__cplusplus** макрос препроцессора **\_\_cplusplus** сообщает обновленное значение поддержки последних стандартов языка C++. По умолчанию Visual Studio всегда возвращает значение 199711L для макроса препроцессора **\_\_cplusplus**.

## <a name="syntax"></a>Синтаксис

> **/Zc:__cplusplus**[ **-** ]

## <a name="remarks"></a>Примечания

Макрос препроцессора **\_\_cplusplus** широко применяется для предоставления сведений о поддержке определенной версии стандарта C++. Так как значительная часть существующего кода требует, чтобы этот макрос имел значение 199711L, компилятор не меняет его, если только вы явно не указали параметр компилятора **/Zc:__cplusplus**. Параметр **/Zc:__cplusplus** доступен начиная с версии 15.7 Visual Studio 2017 и по умолчанию отключен. В более ранних версиях Visual Studio или при указании параметра **/Zc:__cplusplus-** Visual Studio возвращает значение 199711L для макроса препроцессора **\_\_cplusplus**. Это же значение возвращается по умолчанию. Параметр [/permissive-](permissive-standards-conformance.md) не включает параметр **/Zc:__cplusplus**.

Когда параметр **/Zc:__cplusplus** включен, значение, возвращаемое макросом **\_\_cplusplus**, зависит от значения параметра версии [/std](std-specify-language-standard-version.md). В таблице ниже представлены возможные значения макроса.

|Параметр /Zc:__cplusplus|Параметр /std:c++|Значение __cplusplus|
|-|-|-|
Zc:__cplusplus|/std:c++14 (по умолчанию)|201402L
Zc:__cplusplus|/std:c++17|201703L
Zc:__cplusplus|/std:c++latest|201704L
Zc:__cplusplus- (отключено)|Любое значение|199711L
Не указано|Любое значение|199711L

Компилятор не поддерживает параметры стандартов C++98, C++03 и C++11.

Для более детального определения изменений в наборе средств компилятора используйте предварительно определенный макрос [_MSC_VER](../../preprocessor/predefined-macros.md). Значение этого встроенного макроса увеличивается при каждом обновлении набора средств в Visual Studio 2017 и более поздних версий. Предварительно определенный макрос [_MSVC_LANG](../../preprocessor/predefined-macros.md) сообщает версию стандарта независимо от того, включен ли параметр **/Zc:__cplusplus**. Когда параметр **/Zc:__cplusplus** включен, `__cplusplus == _MSVC_LANG`.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Перейдите на страницу свойств **Свойства конфигурации** > **C/C++** > **Командная строка**.

1. Добавьте **/Zc:__cplusplus** или **/Zc:__cplusplus-** в область **Дополнительные параметры**.

## <a name="see-also"></a>См. также

- [/Zc (соответствие)](zc-conformance.md)
- [/std (определение стандартной версии языка)](std-specify-language-standard-version.md)
- [Предустановленные макросы](../../preprocessor/predefined-macros.md)
