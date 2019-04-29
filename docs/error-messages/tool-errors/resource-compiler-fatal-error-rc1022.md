---
title: Неустранимая ошибка компилятора ресурсов RC1022
ms.date: 11/04/2016
f1_keywords:
- RC1022
helpviewer_keywords:
- RC1022
ms.assetid: 30a0f3c7-08a8-4c40-b0de-46ee5feb789d
ms.openlocfilehash: 6ee09105822ea7dd4243741ed00ce36978f09583
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62297285"
---
# <a name="resource-compiler-fatal-error-rc1022"></a>Неустранимая ошибка компилятора ресурсов RC1022

Непредвиденный «#endif»

`#if`, **#Ifdef**, или **#ifndef** директива не заканчивается `#endif` директива.

Убедитесь, что имеется `#if`, **#ifdef**, или **#ifndef** фактически перед этой инструкцией.