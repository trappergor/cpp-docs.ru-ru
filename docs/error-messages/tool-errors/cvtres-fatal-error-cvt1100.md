---
title: Неустранимая ошибка CVTRES CVT1100
ms.date: 11/04/2016
f1_keywords:
- CVT1100
helpviewer_keywords:
- CVT1100
ms.assetid: 886e88dd-5818-4b5f-84f2-d2a3d75f0aaf
ms.openlocfilehash: b7e67df24d41b1e8826673146fcc27fd93d143fd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196551"
---
# <a name="cvtres-fatal-error-cvt1100"></a>Неустранимая ошибка CVTRES CVT1100

дублирующий ресурс — тип: тип, имя: имя, язык: язык, флаги: флаги, размер: размер

Указанный ресурс был указан несколько раз.

Эту ошибку можно получить, если компоновщик создает библиотеку типов и вы не указали [/TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md) , а ресурс в проекте уже использует 1. В этом случае укажите/TLBID и укажите другое число до 65535.
