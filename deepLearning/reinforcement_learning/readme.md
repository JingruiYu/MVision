# 强化学习、反馈学习、遗传学习 自主学习...
[	深度强化学习综述(上)](https://blog.csdn.net/SIGAI_CSDN/article/details/83862597)

[openAI Deep RL 学习](https://spinningup.openai.com/en/latest/)

[CS294-112深度增强学习课程（加州大学伯克利分校 2017） B站视频](https://www.bilibili.com/video/av9802698/)

[CS294-112官方课程主页](http://rail.eecs.berkeley.edu/deeprlcourse/)

[CS294-112官方 github 作业](https://github.com/Ewenwan/homework)

[Deep Reinforcement Learning Hands-On！！！推荐](https://github.com/PacktPublishing/Deep-Reinforcement-Learning-Hands-On)


    人工智能中的很多应用问题需要算法在每个时刻做出决策并执行动作。
    
    1. 对于围棋，每一步需要决定在棋盘的哪个位置放置棋子，以最大可能的战胜对手；
    2. 对于自动驾驶算法，需要根据路况来确定当前的行驶策略以保证安全的行驶到目的地；
    3. 对于机械手，要驱动手臂运动以抓取到设定的目标物体。
    
    这类问题有一个共同的特点：
        要根据当前的条件作出决策和动作，以达到某一预期目标。
        解决这类问题的机器学习算法称为强化学习（reinforcement learning，RL）。
        虽然传统的强化学习理论在过去几十年中得到了不断的完善，
        但还是难以解决现实世界中的复杂问题。
    
# 深度强化学习（DRL，deep reinforcement learning）

    是深度学习与强化学习相结合的产物，
    它集成了深度学习在视觉等感知问题上强大的理解能力，以及强化学习的决策能力，实现了端到端学习。
    深度强化学习的出现使得强化学习技术真正走向实用，得以解决现实场景中的复杂问题。
    从2013年DQN（深度Q网络，deep Q network）出现到目前为止，
    深度强化学习领域出现了大量的算法，以及解决实际应用问题的论文。


# 什么是强化学习

    强化学习是一类特殊的机器学习算法，借鉴于行为主义心理学。
    与有监督学习和无监督学习的目标不同，算法要解决的问题是智能体（agent，即运行强化学习算法的实体）
    在环境中怎样执行动作以获得最大的累计奖励。

    例如，
    对于自动行驶的汽车，强化学习算法控制汽车的动作，保证安全行驶到目的地。
    对于围棋算法，算法要根据当前的棋局来决定如何走子，以赢得这局棋。

    对于第一个问题，
    环境是车辆当前行驶状态（如速度）、路况这样的参数构成的系统的抽象，
    奖励是我们期望得到的结果，即汽车正确的在路面上行驶，到达目的地而不发生事故。

    很多控制、决策问题都可以抽象成这种模型。
    和有监督学习类似，强化学习也有训练过程，需要不断的执行动作，
    观察执行动作后的效果，积累经验形成一个模型。
    与有监督学习不同的是，这里每个动作一般没有直接标定的标签值作为监督信号，
    系统只给算法执行的动作一个反馈，这种反馈一般具有延迟性，
    当前的动作所产生的后果在未来才会完全体现，
    另外未来还具有随机性，例如下一个时刻路面上有哪些行人、车辆在运动，
    算法下一个棋子之后对手会怎么下，都是随机的而不是确定的。
    当前下的棋产生的效果，在一局棋结束时才能体现出来。

    强化学习应用广泛，被认为是通向强人工智能/通用人工智能的核心技术之一。
    所有需要做决策和控制的地方，都有它的身影。
    典型的包括游戏与博弈，如打星际争霸、Atari游戏
    
    自动驾驶系统/无人车：
      算法需要根据当前的路况，无人车自身的状态（如速度、加速度）决定其行驶的行为，如控制方向盘，油门，刹车等。
    机器人控制：
      机器人要根据当前所处的环境，自身的状态，决定其要执行的动作。
      
    所有这些问题总计起来都有一个特点，即
    智能体需要观察环境和自身的状态，
    然后决定要执行的动作，以达到想要的目标
      |———————动作— —————|
      |                 |
    智能体 <-奖励/惩罚---环境
      |——————反馈—————  —| 
      
      
      智能体是强化学习的动作实体。
      对于自动驾驶的汽车，环境是当前的路况；
      对于围棋，状态是当前的棋局。
      在每个时刻，智能体和环境有自己的状态，
      如汽车当前位置和速度，路面上的车辆和行人情况。
      智能体根据当前状态确定一个动作，并执行该动作。
      之后它和环境进入下一个状态，
      同时系统给它一个反馈值，
      对动作进行奖励或惩罚，以迫使智能体执行期望的动作。
  
    
    



