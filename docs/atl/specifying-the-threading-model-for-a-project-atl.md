---
title: Указание потоковой модели для проекта (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 419c9880573c2058b3bb60b9c77e4f3ca065fab7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569888"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Указание потоковой модели для проекта (ATL)

Указание потоковой модели для проекта ATL, доступны следующие макросы:

|Макрос|Рекомендации по использованию|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|Определите, если все объекты использовать один потоковой модели.|
|_ATL_APARTMENT_THREADED|Определите, если один или несколько объектов использовать потоковое.|
|_ATL_FREE_THREADED|Определите, если один или несколько объектов используйте бесплатную или нейтральным работа с потоками. Существующий код может содержать ссылки на эквивалентное макрос [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|

Если для вашего проекта эти макросы не определен, _ATL_FREE_THREADED вступят в силу.

Макросы повлиять на производительность во время выполнения следующим образом:

- Указание макрос, который соответствует объектам в проекте может повысить производительность во время выполнения.

- Указав более высокий уровень макрос, например, при указании _ATL_APARTMENT_THREADED, когда все объекты одного потока, немного снизится производительность во время выполнения.

- Указав более низкого уровня макрос, например, в том случае, если вы укажите _ATL_SINGLE_THREADED, когда один или несколько объектов используйте потоковое или свободной потоковой модели может вызвать сбой во время выполнения приложения.

См. в разделе [параметры, мастер простых объектов ATL](../atl/reference/options-atl-simple-object-wizard.md) threading описание модели, доступные для объекта ATL.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)

