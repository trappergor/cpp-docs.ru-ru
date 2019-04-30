---
title: Ошибка компилятора C3201
ms.date: 11/04/2016
f1_keywords:
- C3201
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
ms.openlocfilehash: 92e068103563f7427de7b394536e72b06fab3374
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402766"
---
# <a name="compiler-error-c3201"></a>Ошибка компилятора C3201

список параметров шаблона для класса-шаблона template не совпадает со списком параметров шаблона для параметра шаблона template

Вы передали шаблон класса в аргументе шаблону класса, не принимающему параметр шаблона, или вы передали несоответствующее число аргументов шаблона для аргумента шаблона по умолчанию.

```
// C3201.cpp
template<typename T1, typename T2>
class X1
{
};

template<template<typename T> class U = X1>   // C3201
class X2
{
};

template<template<typename T, typename V> class U = X1>   // OK
class X3
{
};
```