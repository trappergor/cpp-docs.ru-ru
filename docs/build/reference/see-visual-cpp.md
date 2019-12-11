---
title: '&lt;см > (C++ комментарии к документации)'
ms.date: 11/04/2016
f1_keywords:
- <see>
- see
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
ms.openlocfilehash: 8693646fa37648d1b20c791d99d159f2c81b8ec1
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988620"
---
# <a name="ltseegt"></a>&lt;see&gt;

Тег \<see> позволяет задать ссылку из текста. Используйте тег [\<seealso>](seealso-visual-cpp.md)?/ чтобы указать текст, который должен отображаться в разделе "См. также".

## <a name="syntax"></a>Синтаксис

```
<see cref="member"/>
```

#### <a name="parameters"></a>Параметры

*member*<br/>
Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.  Заключите имя в одинарные или двойные кавычки.

Компилятор проверяет, существует ли элемент кода, и разрешает `member` в имя элемента в выходных XML-данных.  Если компилятору не удается найти `member`, он выдает предупреждение.

## <a name="remarks"></a>Заметки

Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](doc-process-documentation-comments-c-cpp.md).

В разделе [\<summary>](summary-visual-cpp.md) можно найти пример использования тега \<see>.

Компилятор КОМПИЛЯТОРОМ MSVC будет пытаться разрешить ссылки cref в одном проходе через комментарии к документации.  Поэтому если при использовании правил поиска C++ компилятор не найдет символ, ссылка будет помечена как не разрешенная. Дополнительные сведения см. в описании [\<seealso>](seealso-visual-cpp.md).

## <a name="example"></a>Пример

Следующий пример показывает, как можно создать ссылку cref на универсальный тип, чтобы компилятор разрешил ее.

```cpp
// xml_see_cref_example.cpp
// compile with: /LD /clr /doc
// the following cref shows how to specify the reference, such that,
// the compiler will resolve the reference
/// <see cref="C{T}">
/// </see>
ref class A {};

// the following cref shows another way to specify the reference,
// such that, the compiler will resolve the reference
/// <see cref="C < T >"/>

// the following cref shows how to hard-code the reference
/// <see cref="T:C`1">
/// </see>
ref class B {};

/// <see cref="A">
/// </see>
/// <typeparam name="T"></typeparam>
generic<class T>
ref class C {};
```

## <a name="see-also"></a>См. также:

[Документация XML](xml-documentation-visual-cpp.md)
