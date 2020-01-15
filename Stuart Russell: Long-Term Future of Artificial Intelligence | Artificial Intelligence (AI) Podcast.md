# Stuart Russell: Long-Term Future of Artificial Intelligence | Artificial Intelligence (AI) Podcast | Dec 9, 2018







## Introduction by Lex Fridman

The following is a conversation with Stuart Russell. He's a professor of Computer Science at UC Berkeley and a co-author of a book that introduced me -and millions of other people-, to the amazing world of AI called "Artificial Intelligence: A Modern Approach". So, it was an honor for me to have this conversation as part of MIT course and Artificial General Intelligence (AGI), and the Artificial Intelligence podcast. If you enjoy it, please subscribe on YouTube, iTunes, or your podcast provider of choice. Or simply connect with me on Twitter at Lex Friedman, spelled F.R.I.D.M.A.N. And now here's my conversation with Stuart Russell.

[Lex] You've mentioned in 1975, in high school, you've created one year first AI programs that play chess were you ever able to build a program that beat you a chess or another board game?

[Stuart] My program never beat me at chess. I actually wrote the program at Imperial College so I used to take the bus every Wednesday with a box of cards this big and shove them into the card reader and they gave us eight seconds of CPU time. It took about five seconds to read the cards in and compile the code so we had three seconds of CPU time which was enough to make one move you know with a not very deep search and then we would print that move out and then we'd have to go to the back of the queue and wait to feed the cards in again how do you post a search well I would talk to no I think we got we got an eight move eight you know depth eight with alpha beta and we had some tricks of our own about move ordering and some pruning of the tree and we were still able to beat that program yeah yeah I I was a reasonable chess player in my youth I did Anna fellow program and a backgammon program so when I go to Berkeley I worked a lot on what we call meta reasoning which really means reasoning about reasoning and in the case of a game playing program you need to reason about what parts of the search tree you're actually going to explore because the search tree is enormous or you know bigger than the number of atoms in the universe and the
way programs succeed and the way humans succeed is by only looking at a small fraction of the search tree, and if you look at the right fraction you play really well if you look at the wrong fraction if you waste your time thinking about things that are never gonna happen the moves that no one's ever gonna make, then you're gonna lose because you you won't be able to figure out the right decision. So, that question of how machines can manage their own computation either how they decide what to think about is the meta-reasoning question we developed some methods for doing that and very simply a machine should think about whatever thoughts are going to improve its decision quality. We were able to show that both for a fellow which is a standard to play game and for backgammon which includes dice for also it's a two-player game with uncertainty. For both of those cases we could come up with algorithms that were actually much more efficient than the standard alpha-beta search which chess programs at the time we're using and that those programs could beat me and I think you can see same basic ideas in AlphaGo and alpha zero. Today the way they explored the tree is using a former meta reasoning to select what to think about based on how useful it is to think about it.

[Lex] Is there any insights you can describe without Greek symbols of how do we select which paths to go down?

[Stuart] There's really two kinds of learning going on so as you say
AlphaGo learns to evaluate board position so it can it can look at a go
board and it actually has probably a superhuman ability to instantly tell how
promising that situation is. To me the amazing thing about alphago is not that
it can be the world champion with its hands tied behind his back, but the fact
that if you stop it from searching altogether - so, you say: okay you're not
allowed to do any thinking ahead, right? You can just consider each of your
legal moves and then look at the resulting situation and evaluate it so
what we call a depth one search, so just the immediate outcome of your moves and
decide if that's good or bad. That version of Aalphago can still play at a professional level, right? And human professionals are sitting there for five ten minutes deciding what to do, and alphago in less than a second instantly into it what is the right move to make based on its ability to evaluate positions. And that is remarkable because you know we don't have that level of intuition about Go, we actually have to think about the situation. So, anyway that capability that alphago has is one big part of why it beats humans; the other big part is that it's able to look ahead 40, 50, 60 moves into the future. And you know, if it was considering all possibilities -40 or 50 or 60 moves into the future-, that would be you know 10 to the 200 possibility, so way, way more than you know atoms in the universe. And and so on so it's very very selective about what it looks at. so let me try to give you an intuition about how you decide what to think about. It's a combination of two things: one is how promising it is right so if you're
already convinced that a move is terrible there's no point spending a lot
more time convincing yourself that it's terrible because it's probably not gonna
change your mind.So, the the real reason you think is because there's some
possibility of changing your mind about what to do right and is that changing your mind
that would result then in a better final action in the real world so that's the
purpose of thinking is to improve the final action in the real world and so if
you think about a move that is guaranteed to be terrible you can
convince yourself is terrible and you're still not gonna change your mind all
right. But on the other hand you I suppose you had a choice between two moves one of
them you've already figured out is guaranteed to be a draw let's say and
then the other one looks a little bit worse like it looks fairly likely that if you make that move you're gonna lose but there's still some uncertainty about the value of that move there's still some possibility that it will turn out to be a win all right. Then it's worth
thinking about that so even though it's less promising on average than the other
move which is guaranteed to be a draw, there's still some purpose in thinking
about it because there's a chance that you will change your mind and discover
that in fact it's a better move. So it's a combination of how good the move appears to be and how much I'm certainty there is about its value. The more uncertainty, the more it's worth thinking about because there's a higher upside if you want to think of it that way.

[Lex] And of course in the beginning especially in the alphago Zero formulation it's
everything is shrouded in uncertainty so you're really swimming in a sea of
uncertainty so it benefits you too. I mean actually following the same process
as you described but because you're so uncertain about everything you you
basically have to try a lot of different directions?

[Stuart] Yeah. So, the early parts of the search tree a fairly bushy
that it will when looking a lot of different possibilities but fairly
quickly the degree of certainty about some of the moves I mean if a movies are
really terrible you'll pretty quickly find out right you lose half your pieces
or half your territory and and then you'll say okay this this is not worth
thinking about any more and then so a further down the tree becomes very long
and narrow and you're following various lines of play you know 10 20 30 40 50
moves into the future and you know that's again it's something that human
beings have a very hard time doing mainly because they just lacked the
short-term memory. You just can't remember a sequence of moves that's 50
movies long and you can't you can't imagine the board correctly for that
money moves into the future.

[Lex] Of course the top players I'm much more familiar with chess but the top players probably have they have echoes of the same kind of intuition instinct that in a moment's
time alphago applies when they see a board I mean they've seen those patterns human
beings have seen those patterns before at the top at the Grandmaster level. It
seems that there is some similarities or maybe it's it's our imagination creates a vision of those similarities but it feels like this kind of pattern recognition that the alphago approaches are using is similar to what human beings at the top level, what do you think?

[Stuart] I think there's there's some truth to that 

[Lex] But not entirely 

[Stuart Yeah I mean I think the the extent to which a human Grandmaster can
reliably wreak instantly recognize the right move instantly recognize the value
of a position I think that's a little bit overrated ...

[Lex] But if you sacrifice a queen for exam I mean there's these
there's these beautiful games of chess with Bobby Fischer somebody where it's
seeming to make a bad move and I'm not sure there's a a perfect degree of calculation involved where they've calculated all the possible things that happen but there's an
instinct there right that somehow adds up to the 

[Stuart] yeah so I think what happens is you you you get a sense that there's
some possibility in the position even if you make a weird-looking move that it
opens up some some lines of of calculation that otherwise would be
definitely bad and and is that intuition that there's something here in this
position that might might yield a win
down the side 

and then you follow that right and and in some sense when when a
chess player is following a line and in his or her mind they're they mentally
simulating what the other person is gonna do while the opponent is gonna do
and they can do that as long as the moves are kind of forced right as long
as there's a you know there's a fourth we call a forcing variation where the
opponent doesn't really have much choice how to respond and then you see if you
can force them into a situation where you win you know. We see plenty of
mistakes even even in Grandmaster games where they just miss some simple three
four five move combination that you know wasn't particularly apparent in in the
position but we're still there. 

[Lex] That's the thing that makes us human.
yeah so when you mentioned that in a fellow those games were after some meta
reasoning improvements and research I was able to beat you, how did that make
you feel?

[Stuart] Part of the meta reasoning capability that it had was based on learning and and you could sit down the next day and you could just feel that it had got a lot smarter boom you know and all the sudden you really felt like you sort of pressed against
the wall because it was it was much more aggressive and was totally unforgiving
of any minor mistake that you might make and actually it seemed understood
the game better than I did and you know. Gary Kasparov has this quote weary
during his match against deep blue he said he suddenly felt that there was a
new kind of intelligence across the board.

[Lex] Do you think that's a scary or an exciting possibility that's prevent for
yourself in in the context of chess purely sort of in this like that feeling
whatever that is?

[Stuart] I think it's definitely an exciting feeling you know this is what made me work on AI in the first place was as soon as I really understood what a computer was I wanted to make it smart you know I started out with the first program I wrote was for the
Sinclair programmable calculator and i think you could write a 21 step algorithm that was the biggest program you could write something like that and do little arithmetic calculations so I say think I implemented Newton's method for square roots and a few other things like that um but then you know I thought okay if I just had more space I could make this thing intelligent and so I started thinking about AI and and I think the thing that's scary is not is not the chess program because you know chess programs they're not in they're taking over the world business but if you extrapolate ... you know there are things about chess that don't resemble the real world right we know we know the rules of chess chess board is completely visible to the programmer of course the real world is not most you most the real world is not visible from wherever you're sitting so
to speak and to overcome those kinds of problems you need qualitatively different
algorithms another thing about the real world is that you know we we regularly
plan ahead on the timescales involving billions or trillions of steps now we
don't plan that was in detail but you know when you choose to do a PhD at
Berkeley that's a five-year commitment and that amounts to about a trillion motor
control steps that you will eventually be committed to ...

[Lex] Including going up the stairs opening doors drinking water type

[Stuart] I mean every every finger movement while you're typing every character of
every paper and the thesis and everything else so you're not commuting
in advance to the specific motor control steps but you're still reasoning on a
timescale that will eventually reduce to trillions of motor control actions and
so for all these reasons you know alphago and and deep blue and so on don't represent any kind of threat to humanity but they are a step towards it right near that and progress in AI occurs by essentially removing one by one these assumptions that make problems
easy like the assumption of complete observability of the situation right we remove that assumption you need a much more complicated kind of a computing design and you need something that actually keeps track of all the things you can't see and tries to estimate what's going on and there's inevitable uncertainty in that so it becomes a much
more complicated problem but you know we are removing those assumptions we are
starting to have algorithms that can cope with much longer timescales, they can cope with uncertainty they can cope with partial observability and so each of those steps sort of magnifies by a thousand the range of things that we can do with AI systems.

[Lex] so the way I started me I wanted to be a psychiatrist for long time to understand
the mind in high school and of course program and so on and then I showed up
University of Illinois to an AI lab and they said okay I don't have time for you
but here's a book AI a modern approach I think was the first edition at the time
mmm here go go learn this and I remember the lay of the land was well it's
incredible that we solve chess but we'll never solve go I mean it was pretty
certain that go in the way we thought about systems that reason was impossible
to solve and now we've solved this as a very ...

[Stuart] I think I would have said that it's unlikely we could take the kind of
algorithm that was used for chess and just get it to scale up and work well
for go. And at the time what we thought was that in order to solve go we would have to do something similar to the way humans manage the complexity of go which is to
break it down into kind of sub games so when a human thinks about a go board
they think about different parts of the board as sort of weakly connected to
each other and they think about okay within this part of the board here's how
things could go and that part about his how things could go and now you try to
sort of couple those two analyses together and deal with the interactions
and maybe revise your views of how things are going to go in each part and
then you've got maybe five, six, seven, ten parts of the board and that actually
resembles the real world much more than chess does because in the real world you
know we have work, we have home life, we have sport you know whatever different
kinds of activities you know shopping these all are connected to each other
but they're weakly connected so when I'm typing a paper you know I don't simultaneous Li have to decide which order I'm gonna get the you know the milk and
the butter you know that doesn't affect the typing but I do need to realize okay
better finish this before the shops closed because I don't have anything you
don't have any food at home all right right so there's some weak connection
but not in the way that chess works where everything is tied into a single
stream of thought. So the thought was that go just sort of go we'd have to
make progress on stuff that would be useful for the real world and in a way
alphago is a little bit disappointing right because the program designed
for alphago was actually not that different from from deep blue or even
from Arthur Samuels checker playing program from the 1950s and in fact the so the two things that make alphago work is one one is amazing ability ability to evaluate the
positions and the other is the meta-reasoning capability which which
allows it to to explore some paths in the tree very deeply and to abandon
other paths very quickly.

[Lex] So this word meta-reasoning while technically correct inspires perhaps the the wrong degree of power that alphago has for example the word reasonings as a powerful word let me ask you sort of so you were part of the symbolic AI world for a while like
whatever the AI was there's a lot of excellent interesting ideas there that
unfortunately met a winter and so it do you think it really emerges?

[Stuart] well I would say yeah it's not quite as simple as that so the the AI winter so for the first winter that was actually named as such was the one in the late 80s
and that came about because in the mid 80s there was a really a concerted
attempt to push AI out into the real world using what was called expert
system technology and for the most part that technology was just not ready for
primetime. They were trying in many cases to do a form of uncertain reasoning judge you know judgment combinations of evidence diagnosis those kinds of things which
was simply invalid and when you try to apply invalid reasoning methods to real
problems you can fudge it for small versions of the problem but when it
starts to get larger the thing just falls apart so many companies found that
the stuff just didn't work and they were spending tons of money on consultants to
try to make it work and there were you know other practical reasons like you know they they were asking the companies to buy incredibly expensive Lisp machine workstations
which were literally between fifty and a hundred thousand dollars in you know in
1980s money which was would be like between a hundred and fifty and three
hundred thousand dollars per workstation in current prices 

[Lex] so then the bottom line they weren't seeing a profit from it yeah
they in many cases I think there were some successes there's no doubt about
that but people I would say over invested every major company was
starting an AI department just like now
and I worry a bit that we might see
similar disappointments not because the
technology is invalid but it's limited
in its scope and it's almost the the
dual of the you know the scope problems
that expert systems had so what have you
learned from that hype cycle and what
can we do to prevent another winter for
example yeah so when I'm giving talks
these days that's one of the warnings
that I give to to pot warning slide one
is that you know rather than data being
the new oil data is the new snake oil
that's a good line and then and then the
other is that we might see a kind of
very visible failure in some of the
major application areas and I think
self-driving cars would be the flagship
and I think when you look at the history
so the first self-driving car was on the
freeway driving itself changing lanes
overtaking in 1987 and so it's more than
30 years and that kind of looks like
where we are today right you know
prototypes on the freeway changing lanes
and overtaking now I think significant
progress has been made particularly on
the perception side so we worked a lot
on autonomous vehicles in the early mid
90s at Berkley you know and we had our
own big demonstrations you know we we
put congressmen into yourself driving
cars and and had them zooming along the
freeway
and the problem was clearly perception
at the time the problem that perception
yeah so in simulation with perfect
perception you could actually show that
you can drive safely for a long time
even if the other cars are misbehaving
and and so on but simultaneously we
worked on machine vision for detecting
cars and tracking pedestrians and so on
and we couldn't get the reliability of
detection and tracking up to a high
enough particular level particularly in
bad weather conditions nighttime
rainfall good enough for demos but
perhaps not good enough to cover the
general the general yeah the thing about
driving is you know suppose you're a
taxi driver you know and you drive every
day eight hours a day for ten years
right that's a hundred million seconds
of driving you know and any one of those
seconds you can make a fatal mistake so
you're talking about eight nines of
reliability right now if your vision
system only detects ninety eight point
three percent of the vehicles right and
that's sort of you know one on a bit
nines and reliability so you have
another seven orders of magnitude to go
and and this is what people don't
understand they think oh because I had a
successful demo I'm pretty much done but
you know you're not even within seven
orders of magnitude of being done and
that's the difficulty and it's it's not
there can I follow a white line that's
not the problem right we follow a white
line all the way across the country
but it's the it's the weird stuff that
happens it's some of the edge cases yeah
the edge case other drivers doing weird
things you know so if you talk to Google
right so they had actually very
classical architecture where you know
you had machine vision which would
detect all the other cars and
pedestrians and the white lines and the
road signs and then basically that was
fed into a logical database and then you
had a classical 1970s rule-based expert
system telling you okay if you're in the
middle lane and there's a bicyclist in
the right lane who is signaling this
then then then don't need to do that
yeah right and what they found was that
every day they go out and there'd be
another situation that the rules didn't
cover you know so they they come to a
traffic circle and there's a little girl
riding a bicycle the wrong way around a
traffic circle okay what do you do we
don't have a rule oh my god okay stop
and then you know they come back and had
more rules and they just found that this
was not really converging
and and if you think about it right how
how do you deal with an unexpected
situation meaning one that you've never
previously encountered and the sort of
the the reasoning required to figure out
the solution for that situation has
never been done it doesn't match any
previous situation in terms of the kind
of reasoning you have to do well you
know in chess programs this happens all
the time
you're constantly coming up with
situations you haven't seen before and
you have to reason about them you have
to think about okay here are the
possible things I could do here the
outcomes here's how desirable the
outcomes are and then pick the right one
you know in the 90s we were saying okay
this is how you're gonna have to do
automated vehicles they're gonna have to
have a look ahead capability but the
look ahead for driving is more difficult
than it is for chess because Huysmans
the other right there's humans and
they're less predictable than just a
standard well then will you have an
opponent in chess who's also somewhat
unpredictable but for example in chess
you always know the opponent's intention
they're trying to beat you right whereas
in driving you don't know is this guy
trying to turn left or has he just
forgotten to turn off his tone signal or
is he drunk or is he you know changing
the channel on his radio or whatever it
might be you got to try and figure out
the mental state the intent of the other
drivers to forecast the possible
evolutions of their trajectories and
then you've got to figure out okay which
is the directory for me that's going to
be safest and those all interact with
each other because the other drivers
going to react to your trajectory and so
on so you know they've got the classic
merging onto the freeway a problem where
you're kind of racing a vehicle that's
already on the freeway and you are you
gonna pull ahead of them or you're gonna
let them go first and pull in behind and
you get this sort of uncertainty about
who's going first
so all those kinds of things
mean that you need decision-making
architecture that's very different from
either a rule-based system or it seems
to me a kind of an end-to-end neural
network system you know so just as
alphago is pretty good when it doesn't
do any look ahead but it's way way way
way better when it does I think the same
is going to be true for driving you can
have a driving system that's pretty good
when it doesn't do any look ahead but
that's not good enough you know and
we've already seen multiple deaths
caused by poorly designed machine
learning algorithms that don't really
understand what they're doing yeah and
on several levels I think it's on the
perception side there's mistakes being
made by those algorithms were the
perception is very shallow on the
planning side to look ahead like you
said and the thing that we come come up
against that's really interesting when
you try to deploy systems in the real
world is you can't think of an
artificial intelligence system as a
thing that responds to the world always
you have to realize that it's an agent
that others will respond to as well so
in order to drive successfully you can't
just try to do obstacle avoidance you
can't pretend that you're invisible
thank you right you're the invisible car
right just look that way I mean but you
have to assert yet others have to be
scared of you just we're all there's
this tension there's this game so if we
studied a lot of work with pedestrians
if you approach pedestrians as purely an
obstacle avoidance so you either doing
look ahead isn't modeling the intent
that you're you they're not going to
they're going to take advantage of you
they're not going to respect you at all
there has to be a tension a fear some
amount of uncertainty that's how we have
create we or at least just a kind of a
resoluteness right so you have you have
to display a certain amount of
resoluteness you can't you can't be too
tentative
and yeah so the right the the solutions
then become pretty complicated right you
get into game theoretic yes analyses and
so we're you know Berkeley now we're
working a lot on this kind of
interaction between machines and humans
and that's exciting yeah and so my
colleague and could drag an actually you
know if you if you formulate the problem
game theoretically and you just let the
system figure out the solution you know
it does interesting unexpected things
like sometimes at a stop sign
if no one is going first right the car
will actually back up a little all right
and just to indicate to the other cars
that they should go and that's something
it invented entirely by itself that's
interesting you know we didn't say this
is the language of communication at stop
signs it figured it out that's really
interesting
so let me one just step back for a
second just this beautiful philosophical
notion so Pamela I'm a quartic in 1979
wrote AI began with the ancient wish to
forge the gods so when you think about
the history of our civilization do you
think that there is an inherent desire
to create let's not say gods but to
create super intelligence is it inherent
to us is it in our genes that the
natural arc of human civilization is to
create things that are of greater and
greater power and perhaps no echoes of
ourselves so to create the gods as
Pamela said
if the maybe I mean you know we're all
we're all individuals
certainly we see over and over again in
history individuals who thought about
this possibility hopefully when I'm not
being too philosophical here but if you
look at the arc of this you know where
this is going and we'll talk about AI
safety we'll talk about greater and
greater intelligence do you see that
there in when you created the earth
Allah program and you felt this
excitement
what was that excitement was it
excitement of a tinkerer who created
something cool like a clock or was there
a magic or was it more like a child
being born that yeah you know yeah so I
mean I certainly understand that
viewpoint and if you look at the light
he'll report which was commit so in the
70s there was a lot of controversy in
the UK about AI and you know whether it
was for real and how much the money
money the government should invest and
there was a lot long story but the
government commissioned a report by
by light Hill who was a physicist and he
wrote a very damning report about AI
which I think was the point and he said
that that these are you know frustrated
men who unable to have children would
like to create and you know create life
you know as a kind of replacement you
know which I which I think is really
pretty unfair
but there is I mean there there is a
kind of magic I would say you when you
you build something
and what you're building in is really
just you're building in some
understanding of the principles of
learning and decision-making and to see
those principles actually then turn into
intelligent behavior in in specific
situations it's an incredible thing and
you know that is naturally going to make
you think okay where does this end and
so there's a there's magical optimistic
views of word and whatever your view of
optimism is whatever your view of utopia
is it's probably different for everybody
yeah but you've often talked about
concerns you have of how things might go
wrong so I've talked to max tegmark
there's a lot of interesting ways to
think about AI safety you're one of the
seminal people thinking about this
problem among sort of being in the weeds
of actually solving specific AI problems
you also think about the big picture of
where we're going so can you talk about
several elements of it let's just talk
about maybe the control problem so this
idea of losing ability to control the
behavior and of a AI system so how do
you see that how do you see that coming
about what do you think we can do to
manage it well so it doesn't take a
genius to realize that if you make
something that's smarter than you you
might have a problem you know in Turing
Alan Turing you know wrote about the
gave lectures about this you know 19
1951 painted a lecture on the radio and
he basically says you know once the
machine thinking method stops you know
very quickly they'll outstrip humanity
and you know if we're lucky we might be
able to I think he says if we may be
able to turn off the power at strategic
moments but even so a species would be
humbled yeah you can actually I think
was wrong about that right here is you
you know if it's a sufficiently
intelligent machine is not gonna let you
switch it off so it's actually in
competition with you so what do you
think is meant just for a quick tangent
if we shut off this super intelligent
machine that our species will be humbled
I think he means that we would realize
that we are inferior right that we we
only survive by the skin of our teeth
because we happen to get to the off
switch just in time
you know and if we hadn't then we would
have lost control over the earth
so do you are you more worried when you
think about this stuff about super
intelligent AI or are you more worried
about super powerful AI that's not
aligned with our values so the paperclip
scenario is kind of I think so the main
problem I'm working on is is the control
problem the the problem of machines
pursuing objectives that are as you say
not aligned with human objectives and
and this has been it has been the way
we've thought about I eyes since the
beginning you you build a machine for
optimizing and then you put in some
objective and it optimizes right and and
you know we we can think of this as the
the King Midas problem right because if
you know so King Midas put in this
objective right everything I touch you
turned to gold and the gods you know
that's like the machine they said okay
done you know you now have this power
and of course his food and his drink and
his family all turned to gold and then
he's sighs misery and starvation and
this is you know it's it's a warning
it's it's a failure mode that pretty
much every culture in history has had
some story along the same lines you know
there's the the genie that gives you
three wishes and you know third wish is
always you know please undo the first
two wishes because I messed up
and you know and when author Samuel
wrote his chest his checkup laying
program which learned to play checkers
considerably better than Martha Samuel
could play and actually reached a pretty
decent standard
Norbert Wiener who was a one of the
major mathematicians of the 20th century
sort of a father of modern automation
control systems
you know he saw this and he basically
extrapolated you know as Turing did and
said okay this is how we could lose
control and specifically that we have to
be certain that the purpose we put into
the machine as the purpose which we
really desire and the problem is we
can't do that right you mean we're not
it's a very difficult to encode so to
put our values on paper is really
difficult or you're just saying it's
impossible your line is writing this so
it's it theoretically it's possible but
in practice it's extremely unlikely that
we could specify correctly in advance
the full range of concerns of humanity
that you talked about cultural
transmission of values I think is how
humans to human transmission of values
happens right what we learned yeah I
mean as we grow up we learn about the
values that matter how things how things
should go what is reasonable to pursue
and what isn't reasonable to pursue
machines can learn in the same kind of
way yeah so I think that what we need to
do is to get away from this idea that
you build an optimizing machine and you
put the objective into it
because if it's possible that you might
put in a wrong objective and we already
know this is possible because it's
happened lots of times alright that
means that the machine should never take
an objective that's given as gospel
truth
because once it takes them the the
objective is gospel truth alright then
it's the leaves that whatever actions
it's taking in pursuit of that objective
are the correct things to do so you
could be jumping up and down and saying
no you know no no no you're gonna
destroy the world but the machine knows
what the true objective is and it's
pursuing it and tough luck to you you
know and this is not restricted to AI
right this is you know I think many of
the 20th century technologies right so
in statistics you you minimize a loss
function the loss function is
exogenously specified in control theory
you minimize a cost function in
operations research you maximize a
reward function and so on so in all
these disciplines this is how we
conceive of the problem and it's the
wrong problem because we cannot specify
with certainty the correct objective
right we need uncertainty we the machine
to be uncertain about a subjective what
it is that it's post it's my favorite
idea of yours I've heard you say
somewhere well I shouldn't pick
favorites but it just sounds beautiful
we need to teach machines humility yeah
I mean it's a beautiful way to put it I
love it
that they humble oh yeah they know that
they don't know what it is they're
supposed to be doing and that those
those objectives I mean they exist they
are within us but we may not be able to
explicate them we may not even know you
know how we want our future to go so
exactly and the Machine you know a
machine that's uncertain he's going to
be deferential to us so if we say don't
do that well now the machines learn
something a bit more about our true
objectives because something that it
thought was reasonable in pursuit of our
objectives turns out not to be so now
it's learn something so it's going to
defer because it wants to be doing what
we really want
and you know that that point I think is
absolutely central to solving the
control problem and it's a different
kind of AI when you when you take away
this idea that the objective is known
then in fact a lot of the theoretical
frameworks that we're so familiar with
you know Markov decision processes goal
based planning you know standard games
research all of these techniques
actually become inapplicable and you get
a more complicated problem because
because now the interaction with the
human becomes part of the problem
because the human by making choices is
giving you more information about the
'true objective and that information
helps you achieve the objective better
and so that really means that you're
mostly dealing with game theoretic
problems where you've got the machine
and the human and they're coupled
together rather than a machine going off
by itself with a fixed objective which
is fascinating on the machine and the
human level that we when you don't have
an objective means you're together
coming up with an objective I mean
there's a lot of philosophy that you
know you could argue that life doesn't
really have meaning we we together agree
on what gives it meaning and we kind of
culturally create things that give why
the heck we are in this earth anyway we
together as a society create that
meaning and you have to learn that
objective and one of the biggest I
thought that's what you were gonna go
for a second
one of the biggest troubles we've run
into outside of statistics and machine
learning and AI and just human
civilization is when you look at I came
from the south was born in the Soviet
Union and the history of the 20th
century we ran into the most trouble us
humans when there was a certainty about
the objective and you do whatever it
takes to achieve that objective whether
you talking about in Germany or
communist Russia oh yeah I get the
trouble I would say with you know
corporations in fact some people argue
that you know we don't have to look
forward to a time when AI systems take
over the world they already have and
they call corporations right that
corporations happen to be using people
as components right now but they are
effectively algorithmic machines and
they're optimizing an objective which is
quarterly profit that isn't aligned with
overall well-being of the human race and
they are destroying the world they are
primarily responsible for our inability
to tackle climate change right so I
think that's one way
of thinking about what's going on with
with cooperations but I think the point
you're making you is valid that there
are there are many systems in the real
world where we've sort of prematurely
fixed on the objective and then
decoupled the the machine from those
that's supposed to be serving and I
think you see this with government right
government is supposed to be a machine
that serves people but instead it tends
to be taken over by people who have
their own objective and use government
to optimize that objective regardless of
what people want do you have do you find
appealing the idea of almost arguing
machines where you have multiple I
systems with a clear fixed objective we
have in government the red team and the
blue team that are very fixed on their
objectives and they argue and it kind of
maybe it would disagree but it kind of
seems to make it work somewhat that the
the duality of it okay let's go a
hundred years back when there was still
was going on or at the founding of this
country there was disagreement and that
disagreement is where so there's a
balance between certainty and forced
humility because the power was
distributed yeah I think that the the
the nature of debate and disagreement
argument takes as a premise the idea
that you could be wrong right which
means that you're not necessarily
absolutely convinced that your objective
is the correct one right if you were
absolutely Guiness there'll be no point
in having any discussion or argument
because you would never change your mind
and there wouldn't be any any sort of
synthesis or or anything like that so so
I think you can think of argumentation
as a as an implementation of a form of
uncertain reasoning
and you know I I've been reading
recently about utilitarianism in the
history of efforts to define in a sort
of clear mathematical way a
I feel like a formula for moral or
political decision-making and it's
really interesting that the parallels
between the philosophical discussions
going back 200 years and what you see
now in discussions about existential
risk because you it's almost exactly the
same so someone would say okay well
here's a formula for how we should make
decisions right so utilitarianism
you know each person has a utility
function and then we make decisions to
maximize the sum of everybody's utility
mm-hmm right and then people point out
well you know in that case the best
policy is one that leads to the enormous
lis vast population all of whom are
living a life that's barely worth living
right and this is called the repugnant
conclusion and you know another version
is you know that we we should maximize
pleasure and that's what we mean by
utility and then you'll get people
effectively saying well in that case you
know we might as well just have everyone
hooked up to a heroin drip yeah you know
and they didn't use those words but that
debate you know what's happening in the
19th century as it is now about AI that
if we get the formula wrong you know
we're going to have AI systems working
towards an outcome that in retrospect
would be exactly wrong do you think
there's it has beautifully put so the
the echoes are there but do you think I
mean if you look at sam Harris is our
imagination worries about the AI version
of that because of the speed at which
the things going wrong in the
utilitarian context could happen yeah is
that is that a worry for you yeah I I
think that
you know it in most cases not in all but
you know if we if we have a wrong
political idea you know we see it
starting to go wrong and we're you know
we're not completely stupid and so we
said okay that was maybe that was a
mistake
let's try something different and and
also we're very slow and inefficient
about implementing these things and so
on so you have to worry when you have
corporations or political systems that
are extremely efficient
but when we look at AI systems or even
just computers in general right they
have this different characteristic from
ordinary human activity in the past so
let's say you were a surgeon you had
some idea about how to do some operation
right well and let's say you were wrong
all right that that way of doing the
operation would mostly kill the patient
well you'd find out pretty quickly like
after three maybe three or four tries
right
but
that isn't true for pharmaceutical
companies because they don't do three or
four operations they they manufacture
three or four billion pills and they
sell them and then they find out maybe
six months or a year later that oh
people are dying of heart attacks or
getting cancer from this drug and so
that's why we have the FDA right because
of the scalability of pharmaceutical
production and you know and there have
been some unbelievably bad episodes in
the history of pharmaceuticals and and
adulteration of of products and so on
that that have killed tens of thousands
or paralysed hundreds of thousands of
people now with computers we have that
same scalability problem that you can
sit there and type for I equals 1 to 5
billion do right and all of a sudden
you're having an impact on a global
scale and yet we have no FDA right
there's absolutely no controls at all
it's over what a bunch of undergraduates
with too much caffeine can do to the
world and you know we look at what
happened with Facebook well social media
in general and click-through
optimization so you have a simple
feedback algorithm that's trying to just
optimize click-through that sounds
reasonable right because you don't want
to be feeding people ads that they don't
care about I'm not interested in
and you might even think of that process
as simply adjusting the the feeding of
ads or news articles or whatever it
might be to match people's preferences
right which sounds like a good idea but
in fact that isn't how the algorithm
works right you make more money the
algorithm makes more money if it could
better predict what people are going to
click on because then it can feed them
exactly that right so the way to
maximize click-through is actually to
modify the people to make them more
predictable and one way to do that is to
feed them information which will change
their behavior and preferences towards
extremes that make them predictable now
whatever is the nearest extreme or the
nearest predictable point that's where
you're going to end up
the machines will force you there now
and then I think there's a reasonable
argument to say that this among other
things is contributing to the
destruction of democracy in the world
and where was the oversight of this
process where were the people saying
okay you would like to apply this
algorithm to five billion people on the
face of the earth can you show me that
it's safe can you show me that it won't
have various kinds of negative effects
no there was no one asking that question
there was no one placed between you know
the undergrads were too much caffeine
and the human race well it's just they
just did it and but some way outside the
scope of my knowledge so economists
would argue that the what is it the
invisible hand so the the capitalist
system
it was the oversight so if you're going
to corrupt society with whatever
decision you make is a company then
that's going to be reflected in people
not using your product sort of one
that's one model of oversight so we
shall see but you know in the meantime
you know that but you you might even
have broken the political system that
enables capitalism to function well
you've changed it and so we should see
yeah change changes often painful so my
question is uh absolutely it's
fascinating
you're absolutely right that there is
ZERO oversight on algorithms that can
have a profound civilization changing
effect so do you think it's possible I
mean I haven't have you seen government
so do you think it's possible to create
regulatory bodies oversight over AI
algorithms which are inherently such
cutting edge set of ideas and
technologies yeah but I think it takes
time
to figure out what kind of oversight
what kinds of controls I mean took time
to design the FDA regime you know and
some people still don't like it and they
want to fix it
and I think there are clear ways that it
could be improved but the whole notion
that you have stage 1 stage 2 stage 3
and here are the criteria for what you
have to do to pass a stage 1 trial right
we haven't even thought about what those
would be
for algorithms so I mean I think there
are there are things we could do right
now with regard to bias for example we
we have a pretty good technical handle
on how to detect algorithms that are
propagating bias that exists in data
sets how to D by us those algorithms and
and even what it's going to cost you to
do that so I think we could start having
some standards on that I think there are
there are things to do with
impersonation of falsification that we
could we could work on so I thanks ya or
you know in a very simple point so
impersonation ISM is a machine acting as
if it was a person I can't see a real
justification for why we shouldn't
insist that machines self-identify as
machines you know where is the social
benefit in in fooling people into
thinking that this is really a person
when it isn't you know I I don't mind if
it uses a human-like voice that's easy
to understand that's fine
but it should just say I'm a machine in
some some form
people are speaking to that I would
think relatively obvious factors I think
mostly yeah I mean there is actually a
law in California that bans
impersonation but only in certain
restricted circumstances so for the
purpose of engaging in a for Geling
transaction and for the purpose of
modifying someone's voting behavior so
those are those are the circumstances
where machines have to self-identify but
I think this is you know arguably it
should be in all circumstances and then
when you talk about deep fakes you know
we're just beginning but already it's
possible to make a movie of anybody
saying anything in ways that are pretty
hard to detect including yourself
because you're on camera now and your
voice is coming through with high
resolution so you could take what I'm
saying and replaces it with it pretty
much anything else you wanted me to be
saying yeah and even it will change my
lips and expression expressions to fit
and there's actually not much in the way
of real legal protection against that I
think in the commercial area you could
say yeah that's you're using my brand
and so on that there there are rules
about that but in the political sphere I
think it's at the moment it's you know
anything goes so like that could be
really really damaging and let me just
try to make not an argument but try to
look back at history and say something
dark in essence is while regulation
seems to be oversight seems to be
exactly the right thing to do here
it seems that human beings what they
naturally do is they wait for something
to go wrong if you're talking about
nuclear weapons
you can't talk about nuclear weapons
being dangerous until somebody actually
like the United States drops the bomb or
Chernobyl melting do you think we will
have to wait for things going wrong in a
way that's obviously damaging to society
not an existential risk but obviously
damaging or do you have faith that I I
hope not but I mean I think we do have
to look at history and when you know so
the two examples you gave nuclear
weapons and nuclear power are very very
interesting because you know in nuclear
weapons we knew in the early years of
the 20th century that atoms contained a
huge amount of energy right we had e
equals mc-squared we knew the the mass
differences between the different atoms
and their components and we knew that
you might be able to make an incredibly
powerful explosive so HG Wells wrote
science fiction book I think in 1912
Frederick Soddy who was the guy who
discovered isotopes so Nobel Prize
winner he gave a speech in 1915 saying
that
this new explosive would be the
equivalent of 150 tons of dynamite which
turns out to be about right and you know
Kenton this was in World War one right
so he was imagining how much worse the
world would be if we were using that
kind of explosive but the physics
establishment simply refused to believe
that these things could be made
including the people who are making it
well so they were doing the nuclear
physics I mean eventually were the ones
who made it and Rockwell for me or
whoever well so up to the the
development was was mostly theoretical
so it was people using sort of primitive
kinds of particle acceleration and doing
experiments at the at the level of
single particles or collections of
particles they they they want
yet thinking about how to actually make
a bomb or anything like that they but
they knew the energy was there and they
figured if they understood it better it
might be possible but the physics
establishment their view and I think
because they did not want it to be true
their view was that it could not be true
that this could not provide a way to
make a super weapon and you know there
was this famous speech given by
Rutherford who was the sort of leader of
nuclear physics and I was on September
11th 1933 and he he said you know anyone
who talks about the possibility of
obtaining energy from transformation of
atoms is talking complete moonshine and
the next the next morning Leo Szilard
read about that speech and then invented
the nuclear chain reaction and so as
soon as he invented he soon as he had
that idea that you could make a chain
reaction with neutrons because neutrons
were not repelled by the nucleus so they
could enter the nucleus and then
continue the reaction as soon as he has
that idea he instantly realized that the
world was in deep doo-doo because this
is 1933 right you know Hitler had
recently come to power in Germany
Zil odd was in London and eventually
became a refugee and and came to the US
and the in the process of having the
idea about the chain reaction he figured
out basically how to make a bomb and
also how to make a reactor and he
patented the reactor
2:34 but because of the situation the
great power conflict situation that he
could see happening he kept that a
secret and so between then and the
beginning of World War two people were
working including the Germans on how to
actually create Neutron sources right
what specific fission reactions would
produce neutrons of the right energy to
continue the reaction and and that was
demonstrated in Germany I think in 1938
if I remember correctly the first
nuclear weapon patent was 1939 by the
French so this was actually you know
this was actually
going on you know well before World War
two really got going and then you know
the British probably had the most
advanced capability in this area but for
safety reasons among others and blush
which is sort of just resources they
moved the program from Britain to the US
and then that became Manhattan Project
so the the the reason why we couldn't
have any kind of oversight of nuclear
weapons and nuclear technology was
because we were basically already in an
arms race in a war and but you you've
mentioned then in the 20s and 30s so
what are the echoes yeah the way you've
described this story I mean there's
clearly echoes why do you think most a I
researchers
folks who are really close to the metal
they really are not concerned about it
and they don't think about it
whether they don't want to think about
it it's but what are the yeah why do you
think that is what are the echoes of the
nuclear situation to the current
situation and what can we do about it I
think there is a you know a kinda modak
motivated cognition which is a term in
psychology means that you believe what
you would like to be true rather than
what is true and you know it's it's
unsettling to think that what you're
working on might be the end of the human
race obviously so you would rather
instantly deny it
and come up with some reason why it
couldn't be true and the you know I have
I collected a long list of reasons that
extremely intelligent competent AI
scientists have come up with for why we
shouldn't worry about this you know for
example calculators are super human at
arithmetic and they haven't taken over
the world so there's nothing to worry
about well okay my five-year-old you
know could have figured out why that was
an unreasonable and and really quite
weak argument you know another one was
you know you while it's theoretically
possible that you could have superhuman
AI destroy the world you know it's also
theoretically possible that a black hole
could materialize right next to the
earth and destroy humanity I mean yes
it's theoretically possible quantum
theoretically extremely unlikely that it
would just materialize right there but
that's a completely bogus analogy
because you know if the whole physics
community on earth was working to
materialize a black hole in near Earth
orbit right wouldn't you ask them is
that a good idea is that gonna be safe
you know what if you succeed all right
right and that's the thing right the AI
is sort of refused to ask itself what if
you succeed and initially I think that
was because it was too hard but you know
Alan Turing asked himself that and he
said we'd be toast right if we were
lucky we might be able to switch off the
power but probably we'd be toast but
there's also an aspect that because
we're not exactly sure what the future
holds it's not clear exactly so
technically what to worry about sort of
how things go wrong and so there is
something it feels like maybe you can
correct me if I'm wrong but there's
something paralyzing about worrying
about something that logically is
inevitable but you don't really know
what that will look like yeah I think
that's that's it's a reasonable point
and you know the you know it's certainly
in terms of existential risks it's
different from you know asteroid
collides with the earth right right
which again is quite possible you know
it's happened in the past it'll probably
happen again we don't right we don't
know right now but if we did detect an
asteroid that was going to hit the earth
in 75 years time we'd certainly be doing
something about it well it's clear
there's got big rocks we'll probably
have a meeting you see what do we do
about the big rock
will they I write with a I I mean the
very few people who think it's not gonna
happen within the next 75 years
I know rod Brooks doesn't think it's
gonna happen maybe and ruing doesn't
think it's happened but you know a lot
of the people who work day-to-day you
know as you say at the rock face
they think it's gonna happen I think the
median estimate from AI researchers is
somewhere in forty to fifty years from
from now or maybe a little you know I
think in Asia they think it's gonna be
even faster than that I am I'm a little
bit more conservative I think probably
take longer than that but I think it's
you know as happened with nuclear
weapons
well I went overnight it can happen
overnight that you have these
breakthroughs and we need more than one
breakthrough but you know the it's on
the order of half a dozen this is a very
rough scale but so half a dozen
breakthroughs of that nature it would
have to happen for us to reach the
superhuman AI but the you know the AI
research community is vast now the
massive investments from governments
from corporations tons of really really
smart people you know you just have to
look at the rate of progress in
different areas of AI to see that things
are moving pretty fast so to say oh it's
just gonna be thousands of years I don't
see any basis for that you know I see
you know for example the the Stanford
hundred year AI project right which is
supposed to be sort of you know the
serious establishment view their most
recent report actually said it's
probably not even possible
Wow right which if you want a perfect
example of people in denial
that's it because you know for the whole
history of AI we've been saying to
philosophers who said it wasn't possible
well you have no idea what you're
talking about of course it's possible
right give me an give me an argument for
why it couldn't happen and there isn't
one all right and now because people are
worried that maybe a oh it might get a
bad name or or I just don't want to
think about this they're saying okay
well of course it's not really possible
you know and we imagine right imagine if
you know the the leaders of the cancer
biology community got up and said well
you know of course curing cancer it's
not really possible complete outrage and
dismay and you know I I find this really
a strange phenomenon so okay so if you
accept it as possible
and if you accept that it's probably
going to happen
the point that you're making that you
know how does it go wrong a valid
question without that without an answer
to that question then you stuck with
what I call the gorilla problem which is
you know the problem that the gorillas
face right they made something more
intelligent than them namely us a few
million years ago and now now they're in
deep doo-doo yeah so there's really
nothing they can do they've lost the
control theater they failed to solve the
control problem of controlling humans
and so they've lost so we don't want to
be in that situation and if the gorillas
problem is is the only formulation you
have there's not a lot you can do right
other than to say okay we should try to
stop you know we should just not make
the humans or right in this case not
make the AI and I think that's really
hard to do

- I'm not actually proposing that that's
a feasible course of action I also think
that you know if properly control a I
could be incredibly beneficial so the
but it seems to me that there's a
there's a consensus that one of the
major failure modes is this loss of
control that we create AI systems that
are pursuing incorrect objectives and
because the AI system believes it knows
what the objective is it has no
incentive to listen to us anymore
so to speak right it it's just carrying
out the the strategy that it it has
computed as being the optimal solution
and you know it may be that in the
process it needs to acquire more
resources to increase the possibility of
success or prevent various failure modes
by defending itself against interference
and so that collection of problems I
think is something we can address yes
that the other problems are roughly
speaking you know misuse right so even
if we solve the control problem we make
perfectly safe controllable AI systems
well why you know why does dr. evil
going to use those right he wants to
just take over the world and he'll make
unsafe AI system said but then get out
of control so that's one problem which
is sort of a you know a partly a
policing problem
partly a-- a sort of a cultural problem
for the profession of how we teach
people what kinds of AI systems are safe
you talk about autonomous weapon system
and how pretty much everybody agrees
there's too many ways that that can go
horribly wrong if this great slaughter
BOTS movie that kind of illustrates that
beautifully I want to talk that's
another there's another topic I I'm
happy talking about the I just want to
mention that what I see is the third
major failure mode which is overuse not
so much misuse but overuse of AI
that we become overly dependent so I
call this the wooly problems if you seen
wall-e the movie all right all the
humans are on the spaceship and the
machines look after everything for them
and they just watch TV and drink big
gulps and they're all sort of obese and
stupid and they sort of totally lost any
notion of human autonomy and
you know so a in effect right this would
happen like the slow boiling frog right
we would gradually turn over more and
more of the management of our
civilization to machines as we are
already doing in this you know this if
this process continues you know we sort
of gradually switch from sort of being
the Masters of Technology to just being
the guests right so so we become guests
on a cruise ship you know which is fine
for a week but not not further the rest
of eternity right you know and it's
almost irreversible right once you once
you lose the incentive to for example
you know learn to be an engineer or a
doctor or a sanitation operative or or
any other of the the infinitely many
ways that we maintain and propagate our
civilization
you know if you if you don't have the
incentive to do any of that you won't
and then it's really hard to recover and
of course there's just one of the
technologies that could that third
failure mode result in that there's
probably other technology in general
detaches us from it does a bit but the
the the difference is that in terms of
the knowledge to to run our civilization
you know up to now we've had no
alternative but to put it into people's
heads right and if you oh it's not we're
with Google I mean so software in
general so I probably if computers in
general but but the you know the
knowledge of how you know how a
sanitation system works you know that's
an the AI has to understand that it's no
good putting it into Google so I mean we
we've always put knowledge in on paper
but paper doesn't run our civilization
it only runs when it goes from the paper
into people's heads again right so we've
always propagated civilization through
human minds and we've spent about a
trillion person years doing that
literature right you you can work it out
yeah but right is about just over a
hundred billion people who've ever lived
and each of them has spent about ten
years learning stuff and to keep their
civilization going and so that's a
trillion person years we put into this
effort beautiful way to describe all of
civilization and now we're you know
we're danger of throwing that away so
this is a problem that AI console it's
not a technical problem it's a you know
if we do our job right the AI systems
will say you know the human race doesn't
in the long run want to be passengers in
a cruise ship the human race wants
autonomy this is part of human
preferences so we the AI systems are not
going to do this stuff for you you've
got to do it for yourself right I'm not
going to carry you to the top of Everest
in an autonomous helicopter you have to
climb it if you want to get the benefit
and so on so
but I'm afraid that because we are
short-sighted and lazy we're gonna
override the AI systems and and there's
an amazing short story that I recommend
to everyone that I talk to about this
called the machine stops
written in 1909 by Ian Foster who you
know wrote novels about the British
Empire and sort of things that became
costume dramas on the BBC but he wrote
this one science fiction story which is
an amazing vision of the future it has
it has basically iPads it has video
conferencing it has MOOCs
it has computer and computer induced
obesity I mean literally the whole thing
it's what people spend their time doing
is giving online courses or listening to
online courses and talking about ideas
but they never get out there in the real
world that they don't really have a lot
of face-to-face contact everything is
done online
you know so all the things we're
worrying about now were described in
this story and and then the human race
becomes more and more dependent on the
Machine loses knowledge of how things
really run and then becomes vulnerable
to collapse and so it's a it's a pretty
unbelievably amazing story for someone
writing in 1909 to imagine all this loss
yeah so there's very few people that
represent artificial intelligence more
than you Russell so it's all my fault
right you're often brought up as the
person well Stuart Russell like the AI
person is worried about this that's why
you should be worried about it do you
feel the burden of that I don't know if
you feel that at all but when I talk to
people like from you talk about set
people outside of computer science when
they think about this still Russell is
worried about AI safety you should be
worried too do you feel the burden of
that I mean in a practical sense yeah
because I'd yet you know a dozen
sometimes 25 invitations a day
to talk about it to give interviews to
write press articles and so on so in
that very practical sense I'm seeing
that people are concerned and really
interested about this are you worried
that you could be wrong as all good
scientists are of course I worry about
that all the time I mean that's that's
always been the way that I I've worked
you know is like I have an argument in
my head with myself right so I have some
idea and then I think okay how could
that be wrong or did someone else
already have that idea so I'll go and
you know search and as much literature
as I can't to see whether someone else
already thought of that or or even
refuted it so you know I right now I'm
I'm reading a lot of philosophy because
you know in in the form of the debate so
V over utilitarianism and other kinds of
moral moral formulas shall we say people
have already thought through some of
these issues but you know what one of
the things I'm I'm not seeing in a lot
of these debates is this specific idea
about the importance of uncertainty in
the objective that this is the way we
should think about machines that are
beneficial to humans so this idea of
provably beneficial machines based on
explicit uncertainty in the objective
you know it seems to be you know my gut
feeling is this is the core of it it's
gonna have to be elaborated in a lot of
different directions and there are a lot
of lis beneficial yeah but they're I
mean it has to be right we can't afford
you know hand-wavy beneficial yeah
because there are you know whenever we
do hand wavy stuff there are loopholes
and the thing about super intelligent
machines is they find the loopholes you
know just like you know tax evaders if
you don't write your tax law properly
that people will find loopholes and end
up paying no taxes and
and so you should think of it this way
and in getting those definitions right
you know it is really a long process you
know so you can you can define
mathematical frameworks and within that
framework you can prove mathematical
theorems that yes this will you know
this this theoretical entity will be
proven beneficial to that theoretical
entity but that framework may not match
the real world in some crucial way so
long process thinking through it of
iterating and so on the last question
yep you have ten seconds to answer it
what is your favorite sci-fi movie about
AI I would say interstellar has my
favorite robots or beat it Space Odyssey
yeah yeah yeah so so tars the robots one
of the robots in interstellar is the way
a robot should behave
and I would say ex machina is in some
ways the one like the one that makes you
think in a nervous kind of way about a
lot where we're going well Stuart thank
you so much for talking today pleasure
you

