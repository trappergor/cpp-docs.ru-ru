---
title: Классы ссылки шаблонов (C++/CX)
ms.date: 01/22/2017
ms.assetid: a24d5f45-8dbb-4540-958f-c76c90d8ed93
ms.openlocfilehash: 4398cc2c545a57277289a6aa41fc4664d9734eed
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57744344"
---
# <a name="template-ref-classes-ccx"></a>Классы ссылки шаблонов (C++/CX)

Шаблоны C++ не публикуются в метаданных и поэтому не могут иметь быть открытыми или защищенными в программе. Конечно внутри программы можно использовать стандартные шаблоны C++. Кроме того, можно определить закрытый класс ссылки в качестве шаблона и объявить явно специализированный класс ссылки шаблона в качестве закрытого члена открытого класса ссылки.

## <a name="authoring-ref-class-templates"></a>Создание шаблонов классов ссылок

В следующем примере показано, как объявить закрытый класс ссылки в виде шаблона, как объявить стандартный шаблон C++ и как объявить такие класс и шаблон в качестве членов открытого класса ссылки. Обратите внимание, что стандартный шаблон C++ может быть специализирован типом среды выполнения Windows, в данном случае Platform::String ^.

[!code-cpp[cx_templates#01](../cppcx/codesnippet/CPP/templatedemo/class1.h#01)]

## <a name="see-also"></a>См. также

[Система типов (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Справочник по языку Visual C++](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Справочник по пространствам имен](../cppcx/namespaces-reference-c-cx.md)
