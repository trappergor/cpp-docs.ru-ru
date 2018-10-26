---
title: '#Директивы ifdef и #ifndef (C/C++) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#ifndef'
- '#ifdef'
dev_langs:
- C++
helpviewer_keywords:
- '#ifdef directive'
- preprocessor, directives
- ifdef directive (#ifdef)
- ifndef directive (#ifndef)
- '#ifndef directive'
ms.assetid: 2b0be69d-9e72-45d8-8e24-e4130fb2455b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d1ba603941b5d08bc56d8385f2b721fb1bef6586
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075896"
---
# <a name="ifdef-and-ifndef-directives-cc"></a>Директивы #ifdef и #ifndef (C/C++)
**#Ifdef** и **#ifndef** директивы выполните ту же задачу, что `#if` директивы при использовании с **определенные**( *идентификатор* ).

## <a name="syntax"></a>Синтаксис

```
#ifdef identifier
#ifndef identifier

// equivalent to
#if defined identifier
#if !defined identifier
```

## <a name="remarks"></a>Примечания

Можно использовать **#ifdef** и **#ifndef** директивы в любом `#if` может использоваться. **#Ifdef** *идентификатор* оператор эквивалентен `#if 1` при *идентификатор* был определен, и она эквивалентна `#if 0` при *идентификатор* не был определен или не был определен с `#undef` директива. Эти директивы проверяют наличие или отсутствие только идентификаторов, определенных с директивой `#define`, а не идентификаторов, объявленных в исходном коде C или C++.

Эти директивы предназначены только для совместимости с предыдущими версиями языка. **Определенные (** *идентификатор* **)** константное выражение, используемое с `#if` директива является предпочтительным.

**#Ifndef** директива проверяет противоположность условия, проверяемого директивой **#ifdef**. Если идентификатор не определен (или его определение было удалено директивой `#undef`), то условие выполняется (true, ненулевое значение). В противном случае условие не выполняется (false, значение равно 0).

**Блок, относящийся только к системам Microsoft**

*Идентификатор* можно передавать из командной строки с помощью `/D` параметр. Можно указать до 30 макросов с `/D`.

Это позволяет проверить, существует ли определение, поскольку определения можно передавать из командной строки. Пример:

```cpp
// ifdef_ifndef.CPP
// compile with: /Dtest /c
#ifndef test
#define final
#endif
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Директивы препроцессора](../preprocessor/preprocessor-directives.md)