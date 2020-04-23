---
title: Атрибуты (C++/CX)
ms.date: 12/30/2016
ms.assetid: 4438e03c-4de3-433d-abcc-31aa863bc0e0
ms.openlocfilehash: b9e645de021e8618d1dc15a7d58dbbe5998e6fbc
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "82032386"
---
# <a name="attributes-ccx"></a>Атрибуты (C++/CX)

Атрибут — это особый вид класса реф, который может быть подготовл в квадратных скобках к типам и методам Windows Runtime, чтобы указать определенное поведение при создании метаданных. Несколько предопределенных атрибутов, например, [Windows::Foundation::Metadata::WebHostHidden](/uwp/api/windows.foundation.metadata.webhosthiddenattribute)-обычно используются в коде C'/CX. В этом примере показано, как атрибут применяется к классу.

[!code-cpp[cx_attributes#01](../cppcx/codesnippet/CPP/cx_attributes/class1.h#01)]

## <a name="custom-attributes"></a>Настраиваемые атрибуты

Также можно определять настраиваемые атрибуты. Пользовательские атрибуты должны соответствовать этим правилам выполнения Windows:

- настраиваемые атрибуты могут содержать только открытые поля;

- поля настраиваемого атрибута можно инициализировать при применении атрибута к классу;

- поле может относиться к одному из следующих типов:

  - int32 (int)

  - uint32 (unsigned int)

  - bool

  - Platform::String^

  - Windows::Foundation::HResult

  - Platform::Type^

  - public enum class (включая перечисления, определяемые пользователем).

В следующем примере показано, как определить настраиваемый атрибут, а затем инициализировать его при использовании.

[!code-cpp[cx_attributes#02](../cppcx/codesnippet/CPP/cx_attributes/class1.h#02)]

## <a name="see-also"></a>См. также раздел

[Система типов (C++/CX)](../cppcx/type-system-c-cx.md)<br/>
[Ссылка на язык СЗ/CX](../cppcx/visual-c-language-reference-c-cx.md)<br/>
[Ссылка на имены](../cppcx/namespaces-reference-c-cx.md)
