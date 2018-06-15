---
title: /Zc:__cplusplus (включить обновленные __cplusplus-макрос)
ms.custom: ''
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:__cplusplus
dev_langs:
- C++
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a796794c0086b09c15ee88442e0fea4d1b114d98
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2018
ms.locfileid: "34705721"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc:__cplusplus (включить обновленные __cplusplus-макрос)

**/Zc:__cplusplus** включает параметр компилятора  **\_ \_cplusplus** макрос препроцессора сообщить обновленное значение для последней поддержка стандартов языка C++. По умолчанию Visual Studio всегда возвращается значение «199711L»  **\_ \_cplusplus** макрос препроцессора.

## <a name="syntax"></a>Синтаксис

> **/Zc:__cplusplus**[**-**]

## <a name="remarks"></a>Примечания

**\_ \_Cplusplus** макрос препроцессора обычно используется для поддержки отчетов для конкретной версии стандарта C++. Так как большое количество существующий код зависят от значения этого макроса сопоставления «199711L», компилятор не изменяется значение макроса, если вы явно участия в программе с помощью **/Zc:__cplusplus** параметр компилятора. **/Zc:__cplusplus** параметр доступен, начиная с версии 15,7 2017 г. Visual Studio и отключено по умолчанию. В более ранних версиях Visual Studio и по умолчанию или если **/Zc:__cplusplus-** указан, Visual Studio возвращает значение «199711 L» для  **\_ \_cplusplus** макрос препроцессора. [/ Разрешительным-](permissive-standards-conformance.md) параметр не позволяет включить **/Zc:__cplusplus**.

При **/Zc:__cplusplus** параметр включен, в отчете по  **\_ \_cplusplus** зависит от макрос [/std](std-specify-language-standard-version.md) версии коммутатора значение параметра. В этой таблице приведены возможные значения для макроса:

|Коммутатор /Zc:__cplusplus|коммутатор /std:c++|__cplusplus значение|
|-|-|-|
Zc:__cplusplus|/ std: c ++ 14 (по умолчанию)|201402L
Zc:__cplusplus|/ std: c ++ 17|201703L
Zc:__cplusplus|/ std: c ++ последней|201704L
Zc:__cplusplus-(отключено)|Любое значение|199711L
Не указан|Любое значение|199711L

Компилятор не поддерживает стандарты коммутаторы для С ++ 98 C ++ 03 и C ++ 11.

Детальный обнаружения изменений в набор инструментов компилятора, используйте [_MSC_VER](../../preprocessor/predefined-macros.md) предварительно определенный макрос. Значение встроенного макроса увеличивается при каждом обновлении набора средств Visual Studio 2017 г. и более поздних версий. [_MSVC_LANG](../../preprocessor/predefined-macros.md) предварительно определенный макрос сообщает стандартной версии ли **/Zc:__cplusplus** включен или отключен параметр. Когда **/Zc:__cplusplus** включен, `__cplusplus == _MSVC_LANG`.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>Установка параметра компилятора в Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Добавить **/Zc:__cplusplus** или **/Zc:__cplusplus-** для **Дополнительные параметры:** области.

## <a name="see-also"></a>См. также

- [/Zc (соответствие)](zc-conformance.md)
- [/STD (укажите язык стандартной версии)](std-specify-language-standard-version.md)
- [Предустановленные макросы](../../preprocessor/predefined-macros.md)
