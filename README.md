# spamClassify
朴素贝叶斯  垃圾邮件分类

python实现垃圾邮件分类，测试集准确率为96.4%

具体代码及数据集学习了https://github.com/shijing888/BayesSpam 测试集准确率为95.15%

公式原理在其GitHub比较乱，可参考https://blog.csdn.net/starzhou/article/details/76801450， 这里公式比较清晰

上述github地址的作者是完全以上述博客地址来做的，spam_classify是我把作者的代码搬到jupyter notebook实现了

然后spam_new是我在上述作者的代码基础上，用式1来实现的，结果测试集准确率要比式2高一点

下面是我比较疑惑的地方----------------------------------------------------

#P(w|s) ---词w 在垃圾邮件中出现的频次

#P(w|n) ---词w 在正常邮件中出现的频次

pw_s=spamDict[word]/spamFilelen

pw_n=normDict[word]/normFilelen

ps_w=pw_s/(pw_s+pw_n) 

wordProbList.setdefault(word,ps_w)

其实我觉得计算到前两行代码就够了，不应该再计算ps_w=pw_s/(pw_s+pw_n)了吧。因为朴素贝叶斯就是要计算ps_w的，ps_w是计算结果，不是过程里面的吧。ps_w=pw_s/(pw_s+pw_n)这行代码的意义我也没看懂。。。

而且用式2的话有很多参数是预估的，用式1的话，是不需要那么多参数的
