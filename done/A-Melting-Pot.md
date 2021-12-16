# 大熔炉——数据模型+算法模型

## 摘要

>  Leo Breiman的文章《统计建模：两种文化》非常及时，而且具有挑衅性。他主张统计学家学习和欣赏一种不同的“文化”：一种算法方法，不同于熟悉的随机数据建模方法。虽然我们赞赏算法方法并为其做出了贡献，但我们一直也在这两个阵营中涉足。在这里，我们提倡“大熔炉”（melting pot），认为两种方法都有各自的优点，有时可以作用在同一问题上。


我们非常熟悉Leo，钦佩他对我们领域的开创性贡献和对生活的热情 。他最后的主要贡献是随机森林，在他2005年7月去世时，随机森林越来越被广泛使用。我们希望他能看到它现在有多受欢迎。Leo，随机森林已经大杀四方了！

我们在统计学习方面的工作受到了Leo在该文中表达的一些观点的启发，说明我们在很大程度上已经接受了算法建模文化。然而，公平地说，我们在数据建模和算法建模两个阵营中一直都有涉足。我们认为这两种方法都对解决问题有明确的作用和贡献，有时甚至能结合起来解决一个问题。下面我们简单列举几个例子。

- 因果推断是一个热门话题——使用对受试者的观察（非随机）测量来比较两种治疗方法。这不能被视为一个简单的监督学习问题，因为我们无法同时观察给定患者在两种治疗下的结果。此外，任何合理的分析都需要考虑选择带来的偏差。

   目前最先进的方法是概率模型，这种方式需要对潜在的结果和不可混淆性进行假设，同时使用倾向指数。给定这个模型，人们可以使用算法监督学习工具来估计关键成分。然后，估计模型可以用来推断治疗。这个程序很好地说明了用于估计异质性治疗效果。

- 逻辑回归最初在生物统计学和流行病学领域广受欢迎。它的重点是优势比，这是罕见疾病相对风险的一个合理的估计。它有一个很大的优点：它可以从回顾性病例和对照样本中进行估计。这是一个基于贝叶斯公式和条件参数 的概率结果。它允许我们将非随机病例对照标签作为通过逻辑回归估计的目标，并且仍然得到感兴趣参数的有效估计。这也表明，在基于网络的点击率的建模中，我们可以从大量的负样本中抽取子样本，并且仍然可以从逻辑回归中得到有效的预测 。当然，对于这些数据，我们可以使用更复杂的算法模型来拟合我们的数据，但是逻辑回归能告诉我们更多关于我们该如何做的信息。

- Cox比例风险模型 （The Cox proportional hazards model）在生物统计学和流行病学以及金融和工业应用中无处不在。它使用概率半参数框架，巧妙地允许我们对感兴趣的相对风险函数进行建模，同时也允许使用任意的基线风险。概率模型因此确定损失函数，此后允许任何经典或机器学习模型来估计感兴趣的函数。

- 使用概率模型来理解和解释算法模型的行为和性能的例子很多。我们列出了一些：

  - 在支持向量机中，使用铰链损失（hinge-loss）以及一些惩罚项，便可与逻辑回归的对数似然进行直接比较，同时也可以弄明白它们的一些相似性和不同之处。
  - 将Adaboost解释为加法逻辑回归模型（additive logistic regression model），促进了梯度提升（gradient boosting ）的发展。
  - 对机器学习中的“双下降”（double descent）现象，使用简单的参数模型可以给出清晰的解释。



总而言之，数据模型和算法模型都是必不可少的——有时可以一起解决同一个问题——而且我们需要相应的主题专业知识来决定选择其中哪个或者两个都选择。同时数据建模还可以帮助我们更好地理解算法建模的性质。

> 作者 Rob Tibshirani and Trevor Hastie，翻译来自 https://muse.jhu.edu/article/799737