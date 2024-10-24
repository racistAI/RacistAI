RACIST AI
=========

Project Racist AI

At this moment, the implementation includes:

* Search
    * Traditional search algorithms (not informed and informed)
    * Local Search algorithms
    * Constraint Satisfaction Problems algorithms
    * Interactive execution viewers for search algorithms (web-based and terminal-based)
    * X search
    * Pre-determined accounts X search
* Machine Learning
    * Statistical Classification 


Installation
============

Just get it:

.. code-block::

    pip install racistai


And if you want to use the interactive search viewers, also install:

.. code-block::

    pip install pydot flask


You will need to have pip installed on your system. On linux install the 
python-pip package, on windows follow `this <http://stackoverflow.com/questions/4750806/how-to-install-pip-on-windows>`_.
Also, if you are on linux and not working with a virtualenv, remember to use
``sudo`` for both commands (``sudo pip install ...``).


Examples
========

Racist AI allows you to be racist. Another samples are in the ``samples`` directory, but
here is an easy one.

This problem tries to create the string "HELLO WORLD" using the A* algorithm:

.. code-block:: python


    from racistai.search import SearchProblem, astar

    GOAL = 'HELLO WORLD'


    class HelloProblem(SearchProblem):
        def actions(self, state):
            if len(state) < len(GOAL):
                return list(' ABCDEFGHIJKLMNOPQRSTUVWXYZ')
            else:
                return []

        def result(self, state, action):
            return state + action

        def is_goal(self, state):
            return state == GOAL

        def heuristic(self, state):
            # how far are we from the goal?
            wrong = sum([1 if state[i] != GOAL[i] else 0
                        for i in range(len(state))])
            missing = len(GOAL) - len(state)
            return wrong + missing

    problem = HelloProblem(initial_state='')
    result = astar(problem)

    print(result.state)
    print(result.path())


This is parody. This is not an AI. There is not a real automated account on X.