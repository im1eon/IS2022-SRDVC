---
layout: default
---
<!--
# Speech Representation Disentangling with Adversarial Mutual Information Learning for One-shot Voice Conversion


### *Sicheng Yang, Methawee Tantrawenith, Haolin Zhuang, Zhiyong Wu, Aolan Sun, Jianzong Wang, Ning Cheng, Huaizhen Tang, Xintao Zhao, Jie Wang, Helen Meng*
-->
### *Sicheng Yang\*, Methawee Tantrawenith\*, Haolin Zhuang\*, Zhiyong Wu\dagger, Aolan Sun, Jianzong Wang, Ning Cheng, Huaizhen Tang, Xintao Zhao, Jie Wang, Helen Meng*

*\* Equal contribution.*

$ \dagger $ Corresponding author.

# Abstract

One-shot voice conversion (VC) with only a single target speaker speech for reference has become a new research direction. Existing works generally disentangle timbre, while information about pitch, rhythm and content is still mixed together. To perform one-shot VC effectively with further disentangling these speech components, we employ random resampling for pitch and content encoder and use the variational contrastive logratio upper bound of mutual information and gradient reversal layer based adversarial mutual information learning to ensure the different parts of the latent space containing only the desired disentanglement during training. Experiments on the VCTK dataset show the model is a state-of-the-art one-shot VC framework in terms of naturalness and intellgibility of converted speech. In addition, we can transfer style of one-shot VC on timbre, pitch and rhythm separately by speech representation disentanglement.

# Conversion Task

## I. One-shot VC (Timbre Conversion)


<!--
### Source：**_"blabla"_**
<audio controls><source src="./audio/1/F-F/p262_p335_373045/source.wav" type="audio/wav">Your browser does not support the audio element.</audio> 

### Target：**_"blabla"_**
<audio controls><source src="./audio/1/F-F/p262_p335_373045/target.wav" type="audio/wav">Your browser does not support the audio element.</audio> 

| Model Name | Converted Audio |
|:-:|:-:|
| SkipVQVC | <audio controls><source src="./audio/1/F-F/p262_p335_373045/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio> | 
| VQMIVC   | <audio controls><source src="./audio/1/F-F/p262_p335_373045/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>   | 
| AutoVC   | <audio controls><source src="./audio/1/F-F/p262_p335_373045/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>   |    
| AdaIN-VC | <audio controls><source src="./audio/1/F-F/p262_p335_373045/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio> |    
| ClsVC    | <audio controls><source src="./audio/1/F-F/p262_p335_373045/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>    |
| Propose Model |<audio controls><source src="./audio/1/F-F/p262_p335_373045/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
-->

<table>
	<tr>
	    <th align="center" valign="middle">Source Audio</th>
            <th align="center" valign="middle">Target Audio</th>
	    <th align="center" valign="middle">Model</th>
	    <th align="center" valign="middle">Converted Audio</th>  
	</tr >
	<tr >
	    <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/source.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"We felt at the moment, it was not possible."</b></i></p></td>
            <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/target.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"The prognosis is excellent."</b></i></p></td>
	    <td align="center" valign="middle">SkipVQVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">VQMIVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AutoVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AdaIN-VC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
            <td align="center" valign="middle">ClsVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Proposed Model</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-F/p262_p335_373045/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr >
	    <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/source.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"Not one person spoke badly."</b></i></p></td>
            <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/target.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"Gerhard Schroeder was the victor."</b></i></p></td>
	    <td align="center" valign="middle">SkipVQVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">VQMIVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AutoVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AdaIN-VC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
            <td align="center" valign="middle">ClsVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Proposed Model</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/F-M/p264_p278_319303/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr >
	    <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/source.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"It was some time before she found out he was safe."</b></i></p></td>
            <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/target.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"The issues are very intense."</b></i></p></td>
	    <td align="center" valign="middle">SkipVQVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">VQMIVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AutoVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AdaIN-VC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
            <td align="center" valign="middle">ClsVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Proposed Model</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-F/p278_p335_093313/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr >
	    <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/source.wav" type="audio/wav">Your browser does not support the audio element.</audio><br>"They are very clever in their use of words."</td>
            <td rowspan="6" align="center" style="vertical-align:middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/target.wav" type="audio/wav">Your browser does not support the audio element.</audio><br>"The task force continues to be in discussion with both companies."</td>
	    <td align="center" valign="middle">SkipVQVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">VQMIVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AutoVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">AdaIN-VC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
            <td align="center" valign="middle">ClsVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Proposed Model</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/1/M-M/p247_p272_025131/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
</table>

<!--
| Source Audio | Target Audio | SkipVQVC | VQMIVC | AutoVC | AdaIN-VC | ClsVC | Propose Model |
|:-------------|:-------------|:---------|:-------|:-------|:---------|:------|---------------|
| <audio controls><source src="./audio/1/F-F/p262_p335_373045/source.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/F-F/p262_p335_373045/target.wav" type="audio/wav">Your browser does not support the audio element.</audio>        | <audio controls><source src="./audio/1/F-F/p262_p335_373045/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/F-F/p262_p335_373045/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/F-F/p262_p335_373045/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/F-F/p262_p335_373045/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/F-F/p262_p335_373045/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/F-F/p262_p335_373045/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       |
| <audio controls><source src="./audio/1/F-M/p264_p278_319303/source.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/F-M/p264_p278_319303/target.wav" type="audio/wav">Your browser does not support the audio element.</audio>        | <audio controls><source src="./audio/1/F-M/p264_p278_319303/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/F-M/p264_p278_319303/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/F-M/p264_p278_319303/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/F-M/p264_p278_319303/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/F-M/p264_p278_319303/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/F-M/p264_p278_319303/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       |
| <audio controls><source src="./audio/1/M-F/p278_p335_093313/source.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/M-F/p278_p335_093313/target.wav" type="audio/wav">Your browser does not support the audio element.</audio>        | <audio controls><source src="./audio/1/M-F/p278_p335_093313/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/M-F/p278_p335_093313/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/M-F/p278_p335_093313/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/M-F/p278_p335_093313/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/M-F/p278_p335_093313/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/M-F/p278_p335_093313/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       |
| <audio controls><source src="./audio/1/M-M/p247_p272_025131/source.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/M-M/p247_p272_025131/target.wav" type="audio/wav">Your browser does not support the audio element.</audio>        | <audio controls><source src="./audio/1/M-M/p247_p272_025131/My_model.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/M-M/p247_p272_025131/SkipVQVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/M-M/p247_p272_025131/VQMIVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/M-M/p247_p272_025131/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       | <audio controls><source src="./audio/1/M-M/p247_p272_025131/AdaIN-VC.wav" type="audio/wav">Your browser does not support the audio element.</audio>     | <audio controls><source src="./audio/1/M-M/p247_p272_025131/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio>       |
-->


## II. Different Representation Transfer (Not Only Timbre Conversion)

<table>
	<tr>
	    <th align="center" valign="middle">Source Audio</th>
            <th align="center" valign="middle">Target Audio</th>
	    <th align="center" valign="middle">Type</th>
	    <th align="center" valign="middle">Converted Audio</th>  
	</tr >
	<tr >
	    <td rowspan="7" align="center" style="vertical-align:middle"><audio controls><source src="./audio/2/p225_001.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"Please call Stella."</b></i></p></td>
            <td rowspan="7" align="center" style="vertical-align:middle"><audio controls><source src="./audio/2/p232_001.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"Please call Stella."</b></i></p></td>
	    <td align="center" valign="middle">Pitch</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/2/800000_001/p225_p232_001001_F.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Rhythm</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/2/800000_001/p225_p232_001001_R.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/2/800000_001/p225_p232_001001_U.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Pitch+Rhythm</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/2/800000_001/p225_p232_001001_RF.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
            <td align="center" valign="middle">Pitch+Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/2/800000_001/p225_p232_001001_FU.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Rhythm+Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/2/800000_001/p225_p232_001001_RU.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Pitch+Rhythm+Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/2/800000_001/p225_p232_001001_RFU.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
</table>

## III. More

<table>
	<tr>
	    <th align="center" valign="middle">Source Audio</th>
            <th align="center" valign="middle">Target Audio</th>
	    <th align="center" valign="middle">Model</th>
	    <th align="center" valign="middle">Type</th>
	    <th align="center" valign="middle">Converted Audio</th>  
	</tr >
	<tr >
	    <td rowspan="12" align="center" style="vertical-align:middle"><audio controls><source src="./audio/3/source.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"I love Human Computer Speech Interaction Lab."</b></i></p></td>
            <td rowspan="12" align="center" style="vertical-align:middle"><audio controls><source src="./audio/3/target.wav" type="audio/wav">Your browser does not support the audio element.</audio><br><p><i><b>"I love Human Computer Speech Interaction Lab."</b></i></p></td>
	    <td rowspan="7" align="center" style="vertical-align:middle">Proposed Model</td>
	    <td align="center" valign="middle">Pitch</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/source_target_e.ne.n_F.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Rhythm</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/source_target_e.ne.n_R.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/source_target_e.ne.n_U.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Pitch+Rhythm</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/source_target_e.ne.n_RF.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
            <td align="center" valign="middle">Pitch+Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/source_target_e.ne.n_FU.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Rhythm+Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/source_target_e.ne.n_RU.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td align="center" valign="middle">Pitch+Rhythm+Timbre</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/source_target_e.ne.n_RFU.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td colspan="2" align="center" valign="middle">SkipVQVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/HCSI_gen_vqvc_.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td colspan="2" align="center" valign="middle">VQMIVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/VQMIVC_.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td colspan="2" align="center" valign="middle">AutoVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/AutoVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td colspan="2" align="center" valign="middle">AdaIN-VC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/HCSI_gen.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
	<tr>
	    <td colspan="2" align="center" valign="middle">ClsVC</td>
	    <td align="center" valign="middle"><audio controls><source src="./audio/3/ClsVC.wav" type="audio/wav">Your browser does not support the audio element.</audio></td>
	</tr>
</table>

# Code and Pre-trained Model

## I. Code

The code will be uploaded later.

## II. Pre-trained Model

The pre-trained model will be uploaded later.


<!--
| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

## 3

# The code and pre-trained models will be uploaded later.

Text can be **bold**, _italic_, or ~~strikethrough~~.

[Link to another page](./another-page.html).

There should be whitespace between paragraphs.

There should be whitespace between paragraphs. We recommend including a README, or a file with information about your project.

# Header 1

This is a normal paragraph following a header. GitHub is a code hosting platform for version control and collaboration. It lets you and others work together on projects from anywhere.

## Header 2

> This is a blockquote following a header.
>
> When something is important enough, you do it even if the odds are not in your favor.

### Header 3

```js
// Javascript code with syntax highlighting.
var fun = function lang(l) {
  dateformat.i18n = require('./lang/' + l)
  return true;
}
```

```ruby
# Ruby code with syntax highlighting
GitHubPages::Dependencies.gems.each do |gem, version|
  s.add_dependency(gem, "= #{version}")
end
```

#### Header 4

*   This is an unordered list following a header.
*   This is an unordered list following a header.
*   This is an unordered list following a header.

##### Header 5

1.  This is an ordered list following a header.
2.  This is an ordered list following a header.
3.  This is an ordered list following a header.

###### Header 6

| head1        | head two          | three |
|:-------------|:------------------|:------|
| ok           | good swedish fish | nice  |
| out of stock | good and plenty   | nice  |
| ok           | good `oreos`      | hmm   |
| ok           | good `zoute` drop | yumm  |

### There's a horizontal rule below this.

* * *

### Here is an unordered list:

*   Item foo
*   Item bar
*   Item baz
*   Item zip

### And an ordered list:

1.  Item one
1.  Item two
1.  Item three
1.  Item four

### And a nested list:

- level 1 item
  - level 2 item
  - level 2 item
    - level 3 item
    - level 3 item
- level 1 item
  - level 2 item
  - level 2 item
  - level 2 item
- level 1 item
  - level 2 item
  - level 2 item
- level 1 item

### Small image

![Octocat](https://github.githubassets.com/images/icons/emoji/octocat.png)

### Large image

![Branching](https://guides.github.com/activities/hello-world/branching.png)


### Definition lists can be used with HTML syntax.

<dl>
<dt>Name</dt>
<dd>Godzilla</dd>
<dt>Born</dt>
<dd>1952</dd>
<dt>Birthplace</dt>
<dd>Japan</dd>
<dt>Color</dt>
<dd>Green</dd>
</dl>

```
Long, single-line code blocks should not wrap. They should horizontally scroll if they are too long. This line should be long enough to demonstrate this.
```

```
The final element.
```
-->
