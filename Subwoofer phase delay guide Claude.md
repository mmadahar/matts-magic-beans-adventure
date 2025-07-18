# Complete Guide: Dual SVS 3000 Micro Phase and Delay Optimization

## 1. REW Setup and Measurement Procedures with UMIK-1

### Initial UMIK-1 Configuration

Download your microphone’s calibration files from miniDSP’s website using your serial number (format: xxx-yyyy). You’ll receive two files: a regular calibration file and a 90-degree file.  **Use the 90-degree file** for all subwoofer measurements with the microphone pointed at the ceiling. 

### REW Configuration for Your System

1. **Audio Device Settings**:
- Input: Select UMIK-1 specifically (not “Default Device”) 
- Output: Connect to WiiM Ultra via appropriate connection
- Sample Rate: 48 kHz (UMIK-1 fixed rate)  
- Enable WASAPI Exclusive if available  
1. **Critical Windows Settings**:
- Disable all audio enhancements for UMIK-1 in Windows Sound Control Panel  
- Enable “Allow applications to take exclusive control”  
1. **Measurement Parameters**:
- Frequency range: 10-200 Hz for subwoofer-only measurements 
- Sweep level: -20 dB (targeting 75-85 dB SPL)  
- Sweep length: 256k samples for optimal S/N ratio
- Use acoustic timing reference when measuring sub integration with Larsen speakers  

## 2. SVS App Phase Control Implementation (0-180 degrees)

### Understanding SVS 3000 Micro Phase Control

The SVS app provides **continuous phase adjustment from 0-180 degrees** in single-degree increments, far superior to typical receiver switches.  This isn’t simple polarity inversion but true phase adjustment that adds electrical delay to the signal. 

### Step-by-Step SVS App Phase Procedure

1. **Access Phase Control**:
- Open SVS app and select first subwoofer from dropdown
- Tap “Options” → “Phase”
- Adjust slider for 0-180° control
- Tap triangle at bottom to save
1. **Symmetric Placement Optimization**:
- Set both subs to 0° initially 
- Set volume to -15 dB on both 
- Play 80 Hz test tone through system
- Keep Sub 1 at 0°, adjust Sub 2 in 15° increments
- Fine-tune in 5° increments for smoothest response
1. **Key Advantages Over WiiM Phase**:
- Single-degree precision vs. WiiM’s 0°/180° switch only
- Real-time adjustment from listening position
- Independent control of each subwoofer
- Saved presets for different scenarios

## 3. WiiM Ultra Delay Options and Implementation

### Available Delay Controls

The WiiM Ultra offers **0-200ms delay range** adjustable in 1ms increments for precise time alignment.  Access through: Device Settings → Subwoofer → Subwoofer & Speaker Sync.  

### Implementation Methods

1. **Automatic Sync**:
- Uses built-in measurement system  
- Automatically calculates delay differences  
- Good starting point for fine-tuning
1. **Manual Adjustment**:
- 1ms = approximately 1.1 feet of distance 
- Calculate based on physical placement differences
- Apply delay to either mains OR subwoofer output 

### Recommended Settings for Your Setup

- Start with automatic sync feature  
- Fine-tune manually if needed 
- With symmetric placement, minimal delay adjustment typically required
- Focus on SVS phase control for primary alignment

## 4. Measurement Techniques for Symmetric Dual Subs

### Measurement Workflow

1. **Individual Measurements**:
- Measure each SVS 3000 Micro separately 
- Microphone at main listening position, pointed at ceiling 
- Use 90-degree calibration file 
- Document SPL and phase response
1. **Combined Measurement**:
- Enable both subwoofers simultaneously
- Should see 3-6 dB increase over individual measurements
- Check for smooth response without deep nulls
1. **REW Alignment Tool Process**:
- Go to Controls → Alignment Tool 
- Select both individual sub measurements 
- Adjust delay slider to optimize black summed curve 
- Focus on 60-100 Hz range for 80 Hz crossover
- Save aligned sum for reference 

### Symmetric Placement Considerations

- Measure at multiple positions within 2-foot radius of MLP 
- Use REW’s averaging feature for spatial consistency 
- Verify both subs contribute equally at listening position
- Check phase coherence in crossover region

## 5. Measuring and EQing Summed Subwoofer Output

### Proper Summing Technique

1. **Measurement Process**:
- Set both subs to optimized phase settings
- Measure combined output at listening position
- Compare to REW’s predicted sum from Alignment Tool
- Verify 3-6 dB gain over individual measurements
1. **EQ Application Strategy**:
- Use REW’s EQ generation for “Generic” or your DSP type  
- Target gentle house curve (-3 to -6 dB from 20-80 Hz)
- Apply **identical EQ** to both subwoofers
- Maximum 3-5 filters to avoid over-processing
1. **Small Room Considerations**:
- Address room modes with narrow Q filters 
- Avoid boosting nulls (ineffective and wastes power)
- Focus on cutting peaks rather than filling dips
- Use REW’s waterfall plot to identify modal issues 

## 6. Integration with Larsen 4.3 Speakers at 80Hz

### Special Larsen 4.3 Considerations

The Larsen 4.3 extends to **28 Hz (-3dB)**,  unusually low for bookshelf speakers.  This creates unique integration challenges:

1. **Crossover Optimization**:
- Consider 60-70 Hz crossover instead of 80 Hz
- Larsen’s bass extension may overlap significantly at 80 Hz  
- Test both settings with measurements
- Choose based on smoothest transition
1. **Phase Alignment Process**:
- Use acoustic timing reference set to Larsen speaker  
- Measure mains + subs together
- Focus on 40-120 Hz range for integration
- Adjust SVS phase for smoothest response through crossover
1. **WiiM Settings**:
- Set speakers to “Small” with chosen crossover 
- Use 24dB/octave Linkwitz-Riley slopes 
- Disable any additional bass management in WiiM

## 7. Small Room Optimization Techniques

### Placement Strategies for Your Symmetric Setup

1. **Near-Speaker Placement** (Your Current Setup):
- Maintains stereo imaging
- Reduces localization issues
- May require more phase adjustment for smooth response
1. **Alternative Placements to Consider**:
- **1/4 and 3/4 Wall Positions**: Better modal distribution 
- **Opposite Corners**: Maximum modal cancellation 
- Test with REW RTA for real-time feedback 

### Room-Specific Adjustments

1. **Boundary Gain Management**:
- Use SVS app’s Room Gain Compensation if excessive bass 
- Start with -3dB at 25 Hz, Q of 0.7 
- Adjust based on measurements 
1. **Standing Wave Mitigation**:
- Identify room modes with REW 
- Use narrow parametric EQ cuts at modal frequencies 
- Consider acoustic treatment at first reflection points

## 8. Troubleshooting Common Issues

### Phase and Timing Problems

**Issue: Weak Bass Despite Proper Levels**

- **Diagnosis**: Likely phase cancellation 
- **Solution**:
1. Verify polarity with 0°/180° test 
1. Use SVS app to sweep phase while playing 80 Hz tone
1. Find setting with maximum SPL

**Issue: Uneven Bass Across Room**

- **Diagnosis**: Room mode interaction
- **Solution**:
1. Try alternative symmetric placements
1. Adjust phase relationship between subs
1. Apply targeted EQ to problematic frequencies

**Issue: Localization of Bass Sources**

- **Diagnosis**: Phase mismatch or crossover too high
- **Solution**:
1. Ensure identical phase settings if truly symmetric
1. Try lower crossover (60-70 Hz)
1. Verify level matching between subs

### Measurement Verification Checklist

1. **Combined response 3-6 dB higher than individual?** If not, phase issue
1. **Smooth transition through crossover?** Adjust phase if dip present
1. **Consistent response at multiple positions?** Consider placement change if not
1. **Group delay reasonable (<20ms)?** Excessive delay indicates timing issues

### Advanced Troubleshooting with REW

- **Impulse Response**: Peaks should align within 0.5ms 
- **Phase Overlay**: Should track within ±45° through crossover
- **Waterfall Plot**: Check for excessive ringing at specific frequencies
- **Spectrogram**: Visualize time-domain behavior of problematic frequencies

## Final Optimization Workflow

1. **Initial Setup** (30 minutes):
- Position subs symmetrically
- Set both to 0° phase, -15 dB volume 
- Configure WiiM for 80 Hz crossover 
1. **Measurement Phase** (45 minutes):
- Individual sub measurements
- Combined measurement
- Mains + subs integration check
1. **Phase Optimization** (30 minutes):
- Use SVS app with 80 Hz test tone
- Adjust Sub 2 phase for maximum output
- Verify with measurements
1. **Fine-Tuning** (30 minutes):
- Apply calculated delays if needed
- Generate and apply EQ
- Final listening tests

Remember: Your symmetric setup simplifies phase alignment significantly. Focus on **SVS app phase control** for primary optimization, use WiiM delay only if physical placement requires it, and always verify with both measurements and listening tests.
