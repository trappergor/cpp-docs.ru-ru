---
title: '#Директивы ifdef и #ifndef (C/C++) | Документы Microsoft'
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
ms.openlocfilehash: 9a5ecfc9cc63fc4028e1f93d8f30e8d5cb9f9357
ms.sourcegitcommit: 96cdc2da0d8c3783cc2ce03bd280a5430e1ac01d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2018
---
# <a name="ifdef-and-ifndef-directives-cc"></a>Директивы #ifdef и #ifndef (C/C++)
**#Ifdef** и **#ifndef** директивы выполнения той же задачи, как `#if` директива при использовании с **определенные**( *идентификатор* ).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
#ifdef identifier  
#ifndef identifier  
  
// equivalent to  
#if defined identifier  
#if !defined identifier  
```  
  
## <a name="remarks"></a>Примечания  
 Можно использовать **#ifdef** и **#ifndef** директивы в любом `#if` может использоваться. **#Ifdef** *идентификатор* оператор эквивалентен `#if 1` при *идентификатор* определен, и она эквивалентна `#if 0` при *идентификатор* не определен или не было определено с `#undef` директивы. Эти директивы проверяют наличие или отсутствие только идентификаторов, определенных с директивой `#define`, а не идентификаторов, объявленных в исходном коде C или C++.  
  
 Эти директивы предназначены только для совместимости с предыдущими версиями языка. **Определенные (** *идентификатор* **)** константное выражение, используемое с `#if` директива является предпочтительным.  
  
 **#Ifndef** директива проверяет противоположность условия, проверяемого директивой **#ifdef**. Если идентификатор не определен (или его определение было удалено директивой `#undef`), то условие выполняется (true, ненулевое значение). В противном случае условие не выполняется (false, значение равно 0).  
  
 **Блок, относящийся только к системам Microsoft**  
  
 *Идентификатор* можно передать из командной строки, с помощью параметра/d. Он позволяет определить до 30 макросов.  
  
 Это позволяет проверить, существует ли определение, поскольку определения можно передавать из командной строки. Пример:  
  
```  
// ifdef_ifndef.CPP  
// compile with: /Dtest /c  
#ifndef test  
#define final  
#endif  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Директивы препроцессора](../preprocessor/preprocessor-directives.md)