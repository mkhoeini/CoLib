CoLib
=====

A way to collaborate on Data


Motive
------

When you look at how the cyberspace is these days, you'll find out that collaboration is important!
I wanted to do pair programming over the internet, and however I found very great solutions already available today, the lack of a standard and general solution is obvious.

I took the liberty to look at some of them, and saw a familiar pattern. The core of them was trying to solve problems similar to the ones that SCM software, like git, was trying to solve.

Since, previously I gave a thought about how to generalize consepts already present in git in a more versatile manner, the idea of that this ground, i.e. collaborative coding, can be the stoneground of realizing that dream fascinated me. Thus, here we are! :-)


Approach
--------

Here is a collection of ideas, which I hope that someday emerges to good idea for implementation.



### Negotiation

Inspired by [this talk](http://vimeo.com/71278954) I believe that the future of APIs is negotiation.
Thus, the parties taking a part in the collaboration session should be able to extend their own capabilities via doing a conversation with other parties.

The least needed to enable parties to converse is a protocol, And a basic semantical agreement between them. (More to expand on these)


### Data

Data is *The Thing* which parties will enter in collaboration between themselves to get their hands on. Owning data is the source of authority. Other parties will connect to the owner of data to either get their own hands on the data, or to contribute to data.


### History

Data changes over time. Owner of the data might be interested in the history of data, or not. However, whenever other party gets his hand on the data, he also will own his own fork of data and can take his own route of history.

Nevertheless, Histoy is the thing which enables two parties with one piece of data to be able to collaborate. So history can be shared as well.


### Structure

Data has to have structure. Otherwise it would be painfull to talk about how it changed over time. The struture of data is a hierarchical set of typed nodes. With leaves presenting the raw chunks of data.

### Changeset

A change in data is a set of additions, deletions, And/Or replacing a set of nodes. Such a set is a changeset. A changeset represents a relation between two points of history of data.

Therefore, Another representation for data can be a stack of changesets from oblivion to the current point of history. If this stack traveses through every present point of the history of data, then this presentation is of complete history.


Presentation
------------

This is how we present our Data, History, And changesets.

Our data is presented as an immutable datastructure, similar to those that are present in functional programming languages. Which makes it really easy to preserve different points of history with minimal effort.

A Data is a set of nodes. Each node is presented with a unique ID. Which is a hash of its contents. A node contains its author, its creation time, its type, attributes, and its children.

Each point of history is simply The ID of the root node of data.

A changeset is the discription of added, deleted, and updated nodes alongside of the newly introduced nodes.

License
-------

By the way, This work is under the MIT License. See the LICENSE file in the root directory.
