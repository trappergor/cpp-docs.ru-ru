---
title: alloc_text | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
dev_langs:
- C++
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d131cee2194ba139fdb99d9c0fa7ae2c922fe84d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50073820"
---
# <a name="alloctext"></a>alloc_text
Назначает имя разделу кода, в котором должны располагаться заданные определения функций. Директива pragma должна быть между декларатором функции и определением функции для именованных функций.

## <a name="syntax"></a>Синтаксис

```
#pragma alloc_text( "
textsection
", function1, ... )
```

## <a name="remarks"></a>Примечания

**Alloc_text** директива pragma не обрабатывает функций-членов C++ и перегруженные функции. Это применимо только к функциям, объявленным с компоновкой C — то есть функции, объявленные с **extern «C»** спецификация компоновки. При попытке использовать эту директиву pragma в функции с компоновкой C++ возникнет ошибка компилятора.

Поскольку адресация функций при помощи `__based` не поддерживается, указания местоположения разделов необходимо использование **alloc_text** директивы pragma. Имя, указанное в *textsection* должны быть заключены в двойные кавычки.

**Alloc_text** директива pragma должна располагаться после всех объявлений указанных функций и перед их определениями этих функций.

Функции, на которые ссылается **alloc_text** pragma должен быть определен в одном модуле с директивой pragma. В противном случае, если неопределенная функция впоследствии будет скомпилирована в другом разделе текста, ошибка может не быть перехвачена. Хотя в большинстве случаев программа будет выполняться правильно, функция не будет выделена в нужных разделах.

Другие ограничения на **alloc_text** таковы:

- Она не может использоваться внутри функции.

- Она должна использоваться после объявления функции, но перед ее определением.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)