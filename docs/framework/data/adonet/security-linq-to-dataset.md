---
title: "安全性 (LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6116b2b8-75f4-4d8b-aea6-c13e55cda50b
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 305ff1232b21def3c8e7dcb1bec529f81c4e701a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="security-linq-to-dataset"></a>安全性 (LINQ to DataSet)
本主题讨论 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 中的安全性问题。  
  
## <a name="passing-a-query-to-an-untrusted-component"></a>将查询传递到不受信任的组件  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询可在程序中的一点表述，而在另一点执行。 在表述查询的点，查询可引用任何可见元素在该点，例如调用方法所属的类或者表示局部变量/自变量的符号的私有成员。 在执行时，查询能有效访问那些查询在表述中引用的成员，即使其中调用代码没有可见性。 执行查询的代码没有任意添加的可见性，因为它无法选择访问内容。 它能严格访问查询所访问的内容，并且仅通过查询本身访问。  
  
 这意味着将查询的引用传递到其他代码段即表示信任接收该查询的组件，组件可访问查询引用的所有公共成员和私有成员。 通常情况下，不应将 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询传递到不受信任的组件，除非查询已经过仔细构造，使它不能公开应保留为私有的信息。  
  
## <a name="external-input"></a>外部输入  
 应用程序常常采用外部输入（来自用户或其他外部代理），并根据该输入执行操作。  情况下[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]，应用程序可能会构造以某种方式，基于外部输入或输入在查询中使用外部查询。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 查询可在任何接受文本的位置接受参数。 应用程序开发人员应使用参数化查询，而不是将来自外部代理的文本直接注入查询。  
  
 任何直接或间接从用户或外部代理派生的输入都可能包含利用目标语言的语法来执行未授权操作的内容。 这称为 SQL 注入式攻击，是以目标语言为 Transact-SQL 的攻击模式命名的。 恶意用户利用这种直接注入到查询的用户输入删除数据库表、产生拒绝服务或者更改所执行操作的性质。 尽管在 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]中可以撰写查询，但是要通过对象模型 API 执行。 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]通过使用字符串操作或串联，因为它们都是在 TRANSACT-SQL，并不容易受到 SQL 注入式攻击在传统意义上不编写查询。  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
