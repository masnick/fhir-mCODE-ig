<div xmlns="http://www.w3.org/1999/xhtml" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://hl7.org/fhir ../../input-cache/schemas-r5/fhir-single.xsd">

<h3><a name="ReleaseNotes"></a>mCODE Release Notes / Change Log</h3>

<h4>mCODE 1.0 STU1</h4>
<p>The following are changes made to the <a href="http://hl7.org/fhir/us/mcode/2019Sep/">mCODE 0.9.1 September 2019 Ballot Release.</a></p>

<h5>Enhancements</h5>
<ul>
    <li>The following profiles have been added: <em>GeneticSpecimen, RegionStudied</em> to support greater alignment between mCODE and the <a href="http://hl7.org/fhir/uv/genomics-reporting/index.html">Clinical Genomics Reporting FHIR IG STU1.</a>.</li>
    <li>The GeneticVariant profile has additional components which conform to equivalent components in the CG Reporting IG Variant profile: GeneStudied, VariationCode, GenomicDNAChange, GenomicSourceClass, AminoAcidChange, AminoAcidChangeType, CytogeneticLocation, and CytogeneticNomenclature.</li>
    <li>The MedicationStatement profile name has changed to <em>CancerRelatedMedicationStatement</em>. This profile now constrains the reason reference to only primary and secondary cancer conditions.</li>
</ul>

<h5>Corrections and Modifications to Existing Content</h5>
<ul>
    <li>The following mCODE profiles no longer appear and instead document preferred use of FHIR base profiles: <em>BloodPressure</em>, <em>BodyWeight</em>, <em>BodyHeight</em>, <em>CBCWAutoDifferentialPanel</em>, <em>ComprehensiveMetabolic2000SerumOrPlasmaPanel</em>.</li>
    <li>Genomics-related profiles GeneticVariantTested and GeneticVariantFound are combined into one profile, GeneticVariant.</li>
    <li>GenomicsReport onco-core-RegionStudied-extension is migrated to a slice under DiagnosticReport.result with a reference to a new profile, RegionStudied.</li>
    <li>GenomicsReport obf-SpecimenType-extension is migrated to a slice under DiagnosticReport.result with a reference to a new profile, GeneticSpecimen.</li>
    <li>DiagnosticReport.category cardinality changed from 1..1 to 1..*</li>
    <li>Replaced references of CIMPL to references of FHIR Shorthand and SUSHI.</li>
    <li>ECOGPerformanceStatus Observation.code and Observation.interpretation changed to align with the LOINC equivalent of ECOG score (89247-1) and interpretation (LOINC Answer List LL529-9).</li>
    <li>KarnofskyPerformanceStatus Observation.code and Observation.interpretation changed to align with the LOINC equivalent of Karnofsky score (89243-0) and interpretation (LOINC Answer List LL4986-7).</li>
</ul>


<h4>mCODE 0.9.1 September 2019 Ballot Release</h4>
<p>The following are changes relative to <a href="https://mcodeinitiative.github.io/index.html">mCODE 0.9.0.</a></p>

<h5>Enhancements</h5>
<ul>
    <li>Updated to FHIR Release 4 from DSTU 2.</li>
    <li>Changed base class of mCODE laboratory panels (CBC and CMP) from Observation to DiagnosticReport.</li>
    <li>Documented mCODE compliance criteria.</li>
    <li>Documented preferred value sets for extensible binding and affect on US Core compliance.</li>
    <li>Changed HistologyMorphologyBehaviorVS value set to descendants of SCT#367651003 (Malignant neoplasm of primary, secondary, or uncertain origin (morphologic abnormality)), from descendants of SCT#108369006 (Neoplasm (morphologic abnormality)), because the latter brought in some concepts that do not represent malignant neoplasms.</li>
</ul>

<h5>Corrections and Modifications to Existing Content</h5>
<ul>
    <li>Updated code systems to new FHIR R4 base URL, http://terminology.hl7.org (previously was http://hl7.org/fhir)</li>
    <li>Changed profile name from GeneticMutationTested to GeneticVariant.</li>
    <li>Corrected mapping so the reference to PrimaryCancerCondition in all staging-related observations uses the existing 'focus' attribute.</li>
    <li>Eliminated AnatomicalOrientation.</li>
    <li>Eliminated ClockDirection as a separate value set because values are incorporated in logically-defined SNOMED-CT AnatomicalOrientationVS.</li>
    <li>Re-wrote the introductory narratives to consolidate multiple pages.</li>
    <li>Changed clinicalStatus on PrimaryCancerCondition and SecondaryCancerCondition from 1..1 to 0..1.</li>
    <li>Typographical fixes to multiple documentation pages.</li>
    <li>Eliminated reference range from GeneticVariant and components of GeneticVariantFound.</li>
    <li>Improved the definition of "curative" and "palliative" in TreatmentIntentVS.</li>
    <li>Corrected the definition of TreatmentIntent.</li>
    <li>Improved the explanation of the relationships between the genomics-related profiles.</li>
    <li>Updated examples to validate against FHIR R4 and other changes to the profiles.</li>
    <li>Changed blood pressure test code to LNC#85354-9 "Blood pressure panel with all children optional" to align with FHIR</li>
    <li>Restored device attribute on TumorMarkerTest since laboratories do report it on occasion.</li>
    <li>Added string as an allowable datatype for TumorMarkerTest.value[x], since it is a valid datatype for some of the tests included in TumorMarkerTestVS.</li>
    <li>Changed cardinality of ECOGPerformanceStatus.value and KarnofskyPerformanceStatus.value to 1..1 and ECOGPerformanceStatus.dataAbsentReason and ECOGPerformanceStatus.dataAbsentReason to 0..0</li>
    <li>Changed cardinality of GeneticVariant.referenceRange to 0..0.</li>
    <li>Changed cardinality of referenceRange for GeneticVariantFound.component[VariantFoundIdentifier], GeneticVariantFound.component[VariantFoundHGVSName] and GeneticVariantFound.component[VariantFoundDescription] and to 0..0.</li>
    <li>Clarified description of HistologyMorphologyBehaviorVS regarding the use of ICD-O-3 behavior codes.</li>
    <li>Corrected descriptions for multiple codes in the ComorbidConditionVS.</li>
    <li>Updated Data Dictionary to reflect FHIR R4 and other changes to the Implementation Guide.</li>
    <li>Renamed PrimaryCancerConditionVS to PrimaryOrUncertainBehaviorCancerDisorderVS, for greater alignement with value set content.</li>
    <li>Renamed extension prefixes from `shr-core` to `obf-datatype`.</li>
    <li>Replaced onco-core-GeneStudied-extension with observation-geneticsGene standard extension in GeneticVariant.</li>
    <li>Corrected the definition of obf-RadiationDosePerFraction-extension.</li>
    <li>Renamed vital-precondition-extension to vital-preconditionCode-extension to distinguish from precondition whose datatype is Reference().</li>
    <li>Improved the definition for obf-RadiationFractionsDelivered-extension.</li>
    <li>Replaced locally defined LateralityVS with FHIR-defined laterality value set in obf-datatype-Laterality-extension.</li>
    <li>Improved definition of onco-core-EvidenceType-extension.</li>
    <li>Replaced obf-dateOfDiagnosis-extension with condition-assertedDate standard extension in PrimaryCancerCondition and SecondaryCancerCondition.</li>
    <li>Added logical definition to TNM-related value sets to include all codes from AJCC staging systems.</li>
    <li>Removed references to MedicationRequest on basedOn attribute for TNMClinicalPrimaryTumorCategory, TNMClinicalRegionalNodesCategory, TNMClinicalDistantMetastasesCategory, KarnofskyPerformanceStatus and ECOGPerformanceStatus.</li>

</ul>

</div>
