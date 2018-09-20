---
title: Общие изменения в языке (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b48ebdf0bf25399b08f8a1cb1240a857cfad352
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418467"
---
# <a name="general-language-changes-ccli"></a>Общие изменения в языке (C++/CLI)

Ряд функций языка среды CLR, изменено с управляемых расширений для C++ в Visual C++.

Изменения, описанные в этом разделе, представляют собой своего рода набор статей языка. Он включает изменение в обработке строковых литералов, изменение в разрешении перегрузки между многоточие и `Param` атрибут, изменение `typeof` для `typeid`, изменение в вызове списки инициализатора конструктора и Общие сведения о новой нотации приведения, что `safe_cast`.

[Строковый литерал](../dotnet/string-literal.md)<br/>
Описывает, как изменялась обработка строковых литералов.

[Массив Param и многоточие](../dotnet/param-array-and-ellipsis.md)<br/>
Рассматриваются как `ParamArray` теперь получает приоритет над кнопку с многоточием (`...`) для разрешения функций с переменным числом аргументов.

[Переход typeof в T::typeid](../dotnet/typeof-goes-to-t-typeid.md)<br/>
Рассматриваются как `typeof` заменены оператор `typeid`.

[Списки инициализатора](../dotnet/initializer-lists.md)<br/>
Рассматриваются изменения в порядке вызовов списков инициализаторов.

[Нотация приведения типов и знакомство с safe_cast<>](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)<br/>
Рассматриваются изменения в нотации и в частности появлением `safe_cast`.

## <a name="see-also"></a>См. также

[Основы миграции C++/CLI](../dotnet/cpp-cli-migration-primer.md)